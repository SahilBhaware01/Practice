<template>
  <div>
    <h3>Personal Details</h3>
    <b-container fluid>
      <!--       <b-row class="my-1">
        <b-col sm="2">
          <label for="input-default">Full Name:</label>
        </b-col>
        <b-col sm="8">
          <b-form-input
            v-model="Fname"
            type="text"
            id="input-default"
            placeholder="Enter your name"
          ></b-form-input>
        </b-col>
      </b-row>

      <b-row class="my-1">
        <b-col sm="2">
          <label for="input-default">Email:</label>
        </b-col>
        <b-col sm="8">
          <b-form-input
            v-model="email"
            type="text"
            id="input-default"
            placeholder="Enter your email"
          ></b-form-input>
        </b-col>
      </b-row>

      <b-row class="my-1">
        <b-col sm="2">
          <label for="input-default">Mobile:</label>
        </b-col>
        <b-col sm="8">
          <b-form-input
            v-model="mobile"
            type="text"
            id="input-default"
            placeholder="Enter your mobile number"
          ></b-form-input>
        </b-col>
      </b-row>

      <b-row class="my-1">
        <b-col sm="2">
          <label for="input-default">Address:</label>
        </b-col>
        <b-col sm="8">
          <b-form-input
            v-model="address"
            id="input-default"
            type="text"
            placeholder="Enter your address"
          ></b-form-input>
        </b-col>
      </b-row>
      <hr />-->
      <h3>Gradutation</h3>
      <b-row class="my-1">
        <b-col sm="2">
          <label for="input-default"> College:</label>
        </b-col>
        <b-col sm="8">
          <b-form-input
            v-model="college"
            type="text"
            id="input-default"
            placeholder="Enter your college name"
          ></b-form-input>
        </b-col>
      </b-row>
      <b-row class="my-1">
        <b-col sm="2">
          <label for="input-default"> Department:</label>
        </b-col>
        <b-col sm="8">
          <b-form-input
            v-model="Department"
            type="text"
            id="input-default"
            placeholder="Enter your department name"
          ></b-form-input>
        </b-col>
      </b-row>
      <b-row class="my-1">
        <b-col sm="2">
          <label for="input-default">Start Date:</label>
        </b-col>
        <b-col sm="8">
          <b-form-input
            v-model="StartDateGra"
            type="number"
            id="input-default"
            placeholder="Gradutation start date"
          ></b-form-input>
        </b-col>
      </b-row>
      <b-row class="my-1">
        <b-col sm="2">
          <label for="input-default">Finish Date:</label>
        </b-col>
        <b-col sm="8">
          <b-form-input
            v-model="FinishDateGra"
            type="number"
            id="input-default"
            placeholder="Gradutation complete date"
          ></b-form-input>
        </b-col>
      </b-row>
      <b-row class="my-1">
        <b-col sm="2">
          <label for="input-default">Percentage:</label>
        </b-col>
        <b-col sm="8">
          <b-form-input
            v-model="percentageGra"
            type="number"
            id="input-default"
            placeholder="Enter gradutation percentage"
          ></b-form-input>
        </b-col>
      </b-row>

      <hr />
      <!--
     
      <h3>Higher Secondary Education</h3>
      <b-row class="my-1">
        <b-col sm="2">
          <label for="input-default">School:</label>
        </b-col>
        <b-col sm="8">
          <b-form-input
            v-model="school"
            type="text"
            id="input-default"
            placeholder="Enter your college name"
          ></b-form-input>
        </b-col>
      </b-row>
      <b-row class="my-1">
        <b-col sm="2">
          <label for="input-default">Board:</label>
        </b-col>
        <b-col sm="8">
          <b-form-input
            v-model="boardSch"
            type="text"
            id="input-default"
            placeholder="Enter your board name"
          ></b-form-input>
        </b-col>
      </b-row>
      <b-row class="my-1">
        <b-col sm="2">
          <label for="input-default">Start Date:</label>
        </b-col>
        <b-col sm="8">
          <b-form-input
            v-model="StartDateSch"
            type="date"
            id="input-default"
            placeholder="Gradutation start date"
          ></b-form-input>
        </b-col>
      </b-row>
      <b-row class="my-1">
        <b-col sm="2">
          <label for="input-default">Finish Date:</label>
        </b-col>
        <b-col sm="8">
          <b-form-input
            v-model="FinishDateSch"
            type="date"
            id="input-default"
            placeholder="Gradutation complete date"
          ></b-form-input>
        </b-col>
      </b-row>
      <b-row class="my-1">
        <b-col sm="2">
          <label for="input-default">Percentage:</label>
        </b-col>
        <b-col sm="8">
          <b-form-input
            v-model="percentageSch"
            type="number"
            id="input-default"
            placeholder="Enter gradutation percentage"
          ></b-form-input>
        </b-col>
      </b-row>

      <hr />

      <h3>Secondary Education</h3>
      <b-row class="my-1">
        <b-col sm="2">
          <label for="input-default"> College:</label>
        </b-col>
        <b-col sm="8">
          <b-form-input
            v-model="collegename"
            type="text"
            id="input-default"
            placeholder="Enter your college name"
          ></b-form-input>
        </b-col>
      </b-row>
      <b-row class="my-1">
        <b-col sm="2">
          <label for="input-default">Board:</label>
        </b-col>
        <b-col sm="8">
          <b-form-input
            v-model="boardClg"
            type="text"
            id="input-default"
            placeholder="Enter your board name"
          ></b-form-input>
        </b-col>
      </b-row>
      <b-row class="my-1">
        <b-col sm="2">
          <label for="input-default">Start Date:</label>
        </b-col>
        <b-col sm="8">
          <b-form-input
            v-model="StartDateClg"
            type="date"
            id="input-default"
            placeholder="Gradutation start date"
          ></b-form-input>
        </b-col>
      </b-row>
      <b-row class="my-1">
        <b-col sm="2">
          <label for="input-default">Finish Date:</label>
        </b-col>
        <b-col sm="8">
          <b-form-input
            v-model="FinishDateClg"
            type="date"
            id="input-default"
            placeholder="Gradutation complete date"
          ></b-form-input>
        </b-col>
      </b-row>
      <b-row class="my-1">
        <b-col sm="2">
          <label for="input-default">Percentage:</label>
        </b-col>
        <b-col sm="8">
          <b-form-input
            v-model="percentageClg"
            type="number"
            id="input-default"
            placeholder="Enter gradutation percentage"
          ></b-form-input>
        </b-col>  5ffa90e1168c000011e4dc3f
      </b-row>-->
      <b-row>
        <b-col sm="4"></b-col>
        <b-col sm="3">
          <b-button @click="addcandidate">Submit</b-button>
        </b-col>
      </b-row>
    </b-container>
    <hr />

    <b-container fluid> </b-container>

    <hr />
  </div>
</template>
<script>
import gql from "graphql-tag";
export default {
  name: "icons",
  data() {
    return {
      Fname: "",
      email: "",
      mobile: "",
      address: "",
      college: "",
      StartDateGra: "",
      FinishDateGra: "",
      percentageGra: "",
      school: "",
      boardSch: "",
      StartDateSch: "",
      FinishDateSch: "",
      percentageSch: "",
      collegename: "",
      boardClg: "",
      StartDateClg: "",
      FinishDateClg: "",
      percentageClg: "",
      Department: "",
    };
  },
  methods: {
    async addcandidate() {
      const result = await this.$apollo.mutate({
        mutation: gql`
          mutation(
            $candidateId: String
            $college: String
            $specialization: String
            $from: Int
            $to: Int
            $percentage: Int
          ) {
            addUg(
              candidateId: $candidateId
              college: $college
              specialization: $specialization
              from: $from
              to: $to
              percentage: $percentage
            ) {
              candidateId
            }
          }
        `,
        variables: {
          /*candidateName: this.Fname,
          email: this.email,
          phoneNo: this.mobile,
          address: this.address,
          */
          candidateId: "5ffa90e1168c000011e4dc3f",
          college: this.college,
          specialization: this.Department,
          from: parseInt(this.StartDateGra),
          uto: parseInt(this.FinishDateGra),
          percentage: parseInt(this.percentageGra),
          /*
          sslcSchool: this.school,
          sslcBoard: this.boardSch,
          sslcFrom: this.StartDateSch,
          sslcTo: this.FinishDateSch,
          sslcPercentage: this.percentageSch,
          hseSchool: this.collegename,
          hseBoard: this.boardClg,
          hseSpecialization:,
          hseFrom: this.StartDateClg,
          hseTo: this.FinishDateClg,
          hsePercentage: this.percentageClg,*/
        },
      });

      this.$router.push("/");
    },
  },
};
/*  $candidateName: String!
            $email: String!
            $phoneNo: String!
            $address: String!
$ugCollege: String
            $ugSpecialization: String
            $ugFrom: Number
            $ugTo: Number
            $ugPercentage: Number
            $sslcSchool: String
            $sslcBoard: String
            $sslcFrom: Number
            $sslcTo: Number
            $sslcPercentage: Number
            $hseSchool: String
            $hseBoard: String
            $hseSpecialization: String
            $hseFrom: Number
            $hseTo: Number
            $hsePercentage: Number*/
/*  candidateName: $candidateName
              email: $email
              phoneNo: $phoneNo
              address: $address
ugCollege: $ugCollege
              ugSpecialization: $ugSpecialization
              ugFrom: $ugFrom
              ugTo: $ugTo
              ugPercentage: $ugPercentage
              sslcSchool: $sslcSchool
              sslcBoard: $sslcBoard
              sslcFrom: $sslcFrom
              sslcTo: $sslcTo
              sslcPercentage: $sslcPercentage
              hseSchool: $hseSchool
              hseBoard: $hseBoard
              hseSpecialization: $hseSpecialization
              hseFrom: $hseFrom
              hseTo: $hseTo
              hsePercentage: $hsePercentage*/
</script>

<style></style>
