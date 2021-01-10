<template>
  <div>
    <div class="header">
      <h1>Vacancies</h1>
      <button class="add-vacancy">
        <NuxtLink to="/addVancany">Add Vacancy</NuxtLink>
      </button>
    </div>
    <div class="vacancies-list">
      <ul>
        <li v-for="vac in vacancies" :key="vac.id">
          <b-row class="my-1">
            <b-col sm="2"></b-col>
            <b-col sm="7">
              <card>
                <h4>{{ vac.vacancyPost }}</h4>
                <h4>
                  <p class="text-muted">{{ vac.id }}</p>
                </h4>
                <hr />
                <b-row>
                  <b-col sm="3">Start Date</b-col>
                  <b-col sm="3"><h5>20/01/2021</h5></b-col>
                  <b-col sm="3">Apply by </b-col>
                  <b-col sm="3"><h5>10/01/2021</h5></b-col>
                </b-row>
                <br />
                <b-row>
                  <b-col sm="4"
                    >Number of Openings<br /><br />
                    <h6>{{ vac.noOfOpenings }}</h6></b-col
                  >
                  <b-col sm="3"
                    >Duration<br /><br />
                    <h6>{{ vac.duration }} Month</h6></b-col
                  >
                  <b-col sm="3"
                    >Skills <br /><br />
                    <h6>{{ vac.skillsRequired }}</h6></b-col
                  >
                  <b-col sm="3"
                    >perks <br /><br />
                    <h6>{{ vac.perks }}</h6></b-col
                  >
                </b-row>

                <hr />
                <b-row>
                  <b-col sm="3">
                    <b-button sm="3" @click="deletevacancy(vac.id)">Delete</b-button>
                  </b-col>
                  <b-col sm="6"></b-col>
                  <b-col sm="3">
                    <b-button sm="3" variant="info" @click="updatevacancy(vac.id)"
                      >Update</b-button
                    ></b-col
                  >
                </b-row>
              </card>
            </b-col>
          </b-row>
        </li>
      </ul>
      <div>
        <b-modal ref="updateform" hide-footer title="Vacany Update">
          <b-row class="my-1">
            <h3>Edit Vacancy</h3>
            <!--{{ vacancy }}
-->
          </b-row>
          <b-row class="my-1">
            <b-col sm="3">
              <label for="input-default">Vacancy Post:</label>
            </b-col>
            <b-col sm="9">
              <b-form-input
                required
                v-model="UpvacancyPost"
                type="text"
                id="input-default"
                placeholder="Enter vacancy post"
              ></b-form-input>
            </b-col>
          </b-row>
          <b-row class="my-1">
            <b-col sm="3">
              <label for="input-default">Total openings:</label>
            </b-col>
            <b-col sm="9">
              <b-form-input
                required
                v-model="UpnoOfOpenings"
                type="number"
                id="input-default"
                placeholder="Enter total openings"
              ></b-form-input>
            </b-col>
          </b-row>
          <b-row class="my-1">
            <b-col sm="3">
              <label for="input-default">Stipend:</label>
            </b-col>
            <b-col sm="9">
              <b-form-input
                required
                v-model="Upstipend"
                type="number"
                id="input-default"
                placeholder="Enter stipend per month"
              ></b-form-input>
            </b-col>
          </b-row>

          <b-row class="my-3">
            <b-col sm="3"></b-col>
            <b-col sm="2">
              <b-form-checkbox v-model="value1" value="true">Perks</b-form-checkbox>
            </b-col>
          </b-row>
          <b-row class="my-2">
            <b-col sm="3"></b-col>
            <b-col sm="2">
              <b-form-checkbox v-if="value1" v-model="Upvalue2" value="Letter"
                >Letter</b-form-checkbox
              >
            </b-col>
          </b-row>
          <b-row class="my-3">
            <b-col sm="3"></b-col>
            <b-col sm="2">
              <b-form-checkbox v-if="value1" v-model="Upvalue3" value="Certificate"
                >Certificate</b-form-checkbox
              >
            </b-col>
          </b-row>

          <b-row class="my-1">
            <b-col sm="3">
              <label for="input-default">Duration:</label>
            </b-col>
            <b-col sm="9">
              <b-form-input
                required
                v-model="Upduration"
                type="number"
                id="input-default"
                placeholder="Enter duration in months"
              ></b-form-input>
            </b-col>
          </b-row>
          <b-row class="my-1">
            <b-col sm="3">
              <label for="input-default">About Post:</label>
            </b-col>
            <b-col sm="9">
              <b-form-textarea
                required
                v-model="UpaboutPost"
                id="textarea-default"
                placeholder="Enter post description"
              ></b-form-textarea>
            </b-col>
          </b-row>

          <b-row class="my-1">
            <b-col sm="3">
              <label for="input-default">Skills Required:</label>
            </b-col>
            <b-col sm="9">
              <b-form-tags
                required
                input-id="tags-pills"
                v-model="UpskillsRequired"
                tag-variant="dark"
                tag-pills
                size="lg"
                separator=""
                placeholder="Enter new skills separated by space"
              ></b-form-tags>
            </b-col>
          </b-row>
          <hr />
          <b-row class="my-1">
            <b-col sm="3"> </b-col>
          </b-row>
          <b-button class="mt-2" variant="outline-success" block>Submit</b-button>

          <b-button class="mt-3" variant="outline-danger" block @click="hidemodal"
            >Cancel</b-button
          >
        </b-modal>
      </div>
    </div>
  </div>
</template>

<script>
import { BaseAlert } from "@/components";
import gql from "graphql-tag";
export default {
  name: "candidates",
  data() {
    return {
      vacancID: undefined,
      UpvacancyPost: undefined,
      UpnoOfOpenings: undefined,
      Upstipend: undefined,
      perks: [],
      Upduration: undefined,
      UpaboutPost: "",
      UpskillsRequired: [],
      status: true,
      value1: false,
      Upvalue2: "",
      Upvalue3: "",
    };
  },
  mounted() {
    this.getdata();
  },

  components: {
    BaseAlert,
  },
  apollo: {
    vacancies: gql`
      query getVacancies {
        vacancies {
          vacancyPost
          noOfOpenings
          stipend
          perks
          duration
          aboutPost
          skillsRequired
        }
      }
    `,
  },
  methods: {
    async deletevacancy(id) {
      const result = await this.$apollo.mutate({
        mutation: gql`
          mutation($vacancyId: ID!) {
            vacancyDelete(vacancyId: $vacancyId) {
              vacancyPost
            }
          }
        `,
        variables: {
          vacancyId: id,
        },
      });
      this.$router.push("/Vacancies");
    },
    async updatevacancy(id) {
      this.vacancID = id;
      await this.getdata();
      this.showmodal();
    },
    showmodal() {
      this.$refs["updateform"].show();
    },
    hidemodal() {
      this.$refs["updateform"].hide();
    },
    getdata() {
      // console.log(vacancy);
    },
  },
};
</script>

<style>
.header {
  text-align: center;
}

.header h1 {
  display: inline-block;
}

.vacancies-list ul {
  list-style-type: none;
}

.vacancy {
  padding: 23px;
  margin-bottom: 24px;
  border: 1px solid rgb(126, 114, 232);
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.08);
  border-radius: 6px;
}
.vacancy-header {
  margin-bottom: 8px;
  font-size: 18px;
  line-height: 1.33333333;
  font-weight: 600;
}

.add-vacancy {
  position: relative;
  float: right;
  right: 20px;
  top: 10px;
}
</style>
