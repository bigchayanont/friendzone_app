<template>
  <div>
    <div id="create-event" class="popup">
      <div class="popup-section section">
        <div class="popup-form">
          <h1 class="header_title">CREATE NEW EVENT</h1>
          <div id="create-event-section">
            <div id="left">
              <!-- Input -->
              <div>
                <h2 class="input_title">
                  Event Picture
                  <span class="orange-color"> *</span>
                  <span class="orange-color" v-if="invalidEvent_pic">
                    {{ alertEvent_pic }}</span
                  >
                </h2>
                <div id="select-photo-section" class="section">
                  <Upload v-model="event_pic">
                    <div
                      v-if="!event_pic"
                      slot="activator"
                      id="select-photo-inside"
                      class="section"
                    >
                      <img
                        id="addphoto"
                        src="@/assets/icon/icons8-add-image-96.png"
                      />
                      <h1 class="upload">upload photo</h1>
                    </div>
                    <div v-else slot="activator">
                      <img
                        class="pictureUpload"
                        style="position: relative"
                        :src="event_pic.imageURL"
                        alt="event_pic"
                      />
                    </div>
                  </Upload>
                </div>
              </div>
              <!-- Input -->

              <!-- Input -->
              <div>
                <h2 class="input_title">
                  Title
                  <span class="orange-color"> *</span>
                  <span class="orange-color" v-if="invalidTitle">
                    {{ alertTitle }}</span
                  >
                </h2>
                <input
                  v-model="event.title"
                  class="input_box"
                  type="text"
                  maxlength="64"
                  size="64"
                  placeholder="enter your event title"
                />
              </div>
              <!-- Input -->

              <!-- Input -->
              <div>
                <h2 class="input_title">
                  Description
                  <span class="orange-color"> *</span>
                  <span class="orange-color" v-if="invalidDescription">
                    {{ alertDescription }}</span
                  >
                </h2>
                <textarea
                  class="input_textarea_box bio"
                  maxlength="256"
                  size="256"
                  name="bio"
                  placeholder="enter your event description"
                  v-model="event.description"
                >
                </textarea>
              </div>
              <!-- Input -->

              <!-- Input -->
              <div>
                <h2 class="input_title">
                  Location
                  <span class="orange-color"> *</span>
                  <span class="orange-color" v-if="invalidLocation">
                    {{ alertLocation }}</span
                  >
                </h2>
                <input
                  v-model="event.location"
                  class="input_box"
                  type="text"
                  maxlength="128"
                  size="128"
                  placeholder="enter your location"
                />
              </div>
              <!-- Input -->
            </div>
            <div id="right">
              <!-- Input -->
              <div>
                <h2 class="input_title">
                  Start On
                  <span class="orange-color"> *</span>
                  <span class="orange-color" v-if="invalidStartDate">
                    {{ alertStartDate }}</span
                  >
                </h2>
                <div class="date-section">
                  <input
                    id="day"
                    class="date_box_popup"
                    type="text"
                    pattern="[0-9]*"
                    maxlength="2"
                    size="2"
                    v-model="date_start.day"
                    placeholder="day"
                  />
                  <h1 style="margin-left: 10px; color: #e3e3e3">/</h1>
                  <input
                    id="month"
                    style="margin-left: 10px"
                    class="date_box_popup"
                    type="text"
                    pattern="[0-9]*"
                    maxlength="2"
                    size="2"
                    v-model="date_start.month"
                    placeholder="month"
                  />
                  <h1 style="margin-left: 10px; color: #e3e3e3">/</h1>
                  <input
                    id="year"
                    style="margin-left: 10px"
                    class="date_box_popup"
                    type="text"
                    pattern="[0-9]*"
                    maxlength="4"
                    size="4"
                    v-model="date_start.year"
                    placeholder="year"
                  />
                </div>
                <div class="time-section">
                  <input
                    id="h1"
                    class="date_box_popup"
                    type="text"
                    pattern="[0-9]*"
                    maxlength="1"
                    size="1"
                    v-model="date_start.h1"
                    placeholder="0"
                  />
                  <input
                    id="h2"
                    style="margin-left: 10px"
                    class="date_box_popup"
                    type="text"
                    pattern="[0-9]*"
                    maxlength="1"
                    size="1"
                    v-model="date_start.h2"
                    placeholder="0"
                  />
                  <h1
                    style="
                    font-size: 3em;
                    margin-top: 5px;
                    margin-left: 10px;
                    color: #e3e3e3;
                  "
                  >
                    :
                  </h1>
                  <input
                    id="m1"
                    style="margin-left: 10px"
                    class="date_box_popup"
                    type="text"
                    pattern="[0-9]*"
                    maxlength="1"
                    size="1"
                    v-model="date_start.m1"
                    placeholder="0"
                  />
                  <input
                    id="m2"
                    style="margin-left: 10px"
                    class="date_box_popup"
                    type="text"
                    pattern="[0-9]*"
                    maxlength="1"
                    size="1"
                    v-model="date_start.m2"
                    placeholder="0"
                  />
                </div>
              </div>
              <!-- Input -->

              <!-- Input -->
              <div>
                <h2 class="input_title">
                  End On
                  <span class="orange-color"> *</span>
                  <span class="orange-color" v-if="invalidEndDate">
                    {{ alertEndDate }}</span
                  >
                </h2>
                <div class="date-section">
                  <input
                    id="day"
                    class="date_box_popup"
                    type="text"
                    pattern="[0-9]*"
                    maxlength="2"
                    size="2"
                    v-model="date_end.day"
                    placeholder="day"
                  />
                  <h1 style="margin-left: 10px; color: #e3e3e3">/</h1>
                  <input
                    id="month"
                    style="margin-left: 10px"
                    class="date_box_popup"
                    type="text"
                    pattern="[0-9]*"
                    maxlength="2"
                    size="2"
                    v-model="date_end.month"
                    placeholder="month"
                  />
                  <h1 style="margin-left: 10px; color: #e3e3e3">/</h1>
                  <input
                    id="year"
                    style="margin-left: 10px"
                    class="date_box_popup"
                    type="text"
                    pattern="[0-9]*"
                    maxlength="4"
                    size="4"
                    v-model="date_end.year"
                    placeholder="year"
                  />
                </div>
                <div class="time-section">
                  <input
                    id="h1"
                    class="date_box_popup"
                    type="text"
                    pattern="[0-9]*"
                    maxlength="1"
                    size="1"
                    v-model="date_end.h1"
                    placeholder="0"
                  />
                  <input
                    id="h2"
                    style="margin-left: 10px"
                    class="date_box_popup"
                    type="text"
                    pattern="[0-9]*"
                    maxlength="1"
                    size="1"
                    v-model="date_end.h2"
                    placeholder="0"
                  />
                  <h1
                    style="
                    font-size: 3em;
                    margin-top: 5px;
                    margin-left: 10px;
                    color: #e3e3e3;
                  "
                  >
                    :
                  </h1>
                  <input
                    id="m1"
                    style="margin-left: 10px"
                    class="date_box_popup"
                    type="text"
                    pattern="[0-9]*"
                    maxlength="1"
                    size="1"
                    v-model="date_end.m1"
                    placeholder="0"
                  />
                  <input
                    id="m2"
                    style="margin-left: 10px"
                    class="date_box_popup"
                    type="text"
                    pattern="[0-9]*"
                    maxlength="1"
                    size="1"
                    v-model="date_end.m2"
                    placeholder="0"
                  />
                </div>
              </div>
              <!-- Input -->

              <!-- Input -->
              <div>
                <h2 class="input_title">
                  Preferred Participant Gender
                  <span class="orange-color"> *</span>
                  <span class="orange-color" v-if="invalidGender">
                    {{ alertGender }}</span
                  >
                </h2>
                <multiselect
                  v-model="gender_value"
                  placeholder="select your preferred gender"
                  label="name"
                  track-by="code"
                  :options="gender_options"
                  :multiple="true"
                ></multiselect>
              </div>
              <!-- Input -->

              <!-- Input -->
              <div>
                <h2 class="input_title">
                  Event Category
                  <span class="orange-color"> *</span>
                  <span class="orange-color" v-if="invalidCategory">
                    {{ alertCategory }}</span
                  >
                </h2>
                <multiselect
                  v-model="category_value"
                  placeholder="select event category"
                  label="name"
                  track-by="code"
                  :options="category_options"
                  :multiple="true"
                  :max="3"
                ></multiselect>
              </div>
              <!-- Input -->

              <div>
                <div id="participant-section">
                  <!-- Input -->
                  <div>
                    <h2 class="input_title">
                      Max Participants
                      <span class="orange-color"> *</span>
                    </h2>
                    <h2 v-if="invalidParticipants" class="orange-color">
                      {{ alertParticipants }}
                    </h2>
                    <input
                      v-model="event.max_participant"
                      class="input_participant"
                      type="text"
                      maxlength="5"
                      size="5"
                      placeholder="Max amount"
                    />
                  </div>
                  <!-- Input -->

                  <!-- Input -->
                  <div>
                    <h2 class="input_title">
                      Age Limits
                      <span class="orange-color"> *</span>
                    </h2>
                    <h2 v-if="invalidAge" class="orange-color">
                      {{ alertAge }}
                    </h2>
                    <div class="section">
                      <input
                        v-model="event.min_age"
                        class="input_age"
                        type="text"
                        maxlength="2"
                        size="2"
                        placeholder="min"
                      />
                      <h1 class="input_title" id="to">to</h1>
                      <input
                        v-model="event.max_age"
                        class="input_age"
                        type="text"
                        maxlength="2"
                        size="2"
                        placeholder="max"
                      />
                    </div>
                  </div>
                  <!-- Input -->
                </div>
              </div>
            </div>
          </div>

          <div class="button-section">
            <div>
              <button class="back_button" @click="createdReturn()">
                Cancel
              </button>
            </div>
            <div>
              <button class="create_button" @click="ClickCreate()">
                Create Now
              </button>
            </div>
          </div>

          <img
            @click="createdReturn()"
            style="cursor: pointer"
            class="close"
            src="@/assets/icon/icons8-multiply-96.png"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<style src="vue-multiselect/dist/vue-multiselect.min.css"></style>

<script>
import $ from "jquery";
import Multiselect from "vue-multiselect";
import Event from "./../../models/event";
import GenderService from "../../services/gender.service";
import CategoryService from "../../services/category.service";
import EventService from "../../services/event.service";
import Upload from "@/components/UploadPic.vue";
import decode from "jwt-decode";

class constructDate {
  constructor(date) {
    this.day = date.day;
    this.month = date.month;
    this.year = date.year;
    this.h1 = date.h1;
    this.h2 = date.h2;
    this.m1 = date.m1;
    this.m2 = date.m2;
  }
}

class Pick {
  constructor(pick) {
    this.name = pick.name;
    this.code = pick.code;
  }
}

export default {
  data() {
    return {
      genderList: [],
      categoryList: [],
      date_start: new constructDate(""),
      date_end: new constructDate(""),
      hs: "",
      ms: "",
      he: "",
      me: "",
      event_id: null,
      event_pic: "",
      event: new Event({
        host_id: "",
        title: "",
        description: "",
        location: "",
        event_pic: "",
        start_at: "",
        end_at: "",
        max_participant: "",
        min_age: "",
        max_age: ""
      }),
      gender_value: [],
      gender_options: [],
      category_value: [],
      category_options: [],
      role: "",
      invalidEvent_pic: false,
      invalidTitle: false,
      invalidDescription: false,
      invalidLocation: false,
      invalidStartDate: false,
      invalidEndDate: false,
      invalidGender: false,
      invalidCategory: false,
      invalidParticipants: false,
      invalidAge: false,
      alertEvent_pic: "",
      alertTitle: "",
      alertDescription: "",
      alertLocation: "",
      alertStartDate: "",
      alertEndDate: "",
      alertGender: "",
      alertCategory: "",
      alertParticipants: "",
      alertAge: ""
    };
  },
  components: {
    Multiselect,
    Upload
  },
  watch: {
    event_pic: function() {
      this.invalidEvent_pic = false;
    },
    "event.title": function() {
      this.invalidTitle = false;
    },
    "event.description": function() {
      this.invalidDescription = false;
    },
    "event.location": function() {
      this.invalidLocation = false;
    },
    "date_start.day": function() {
      this.invalidStartDate = false;
    },
    "date_start.month": function() {
      this.invalidStartDate = false;
    },
    "date_start.year": function() {
      this.invalidStartDate = false;
    },
    "date_end.day": function() {
      this.invalidEndDate = false;
    },
    "date_end.month": function() {
      this.invalidEndDate = false;
    },
    "date_end.year": function() {
      this.invalidStartDate = false;
    },
    "date_start.h1": function() {
      this.invalidStartDate = false;
    },
    "date_start.h2": function() {
      this.invalidStartDate = false;
    },
    "date_start.m1": function() {
      this.invalidStartDate = false;
    },
    "date_start.m2": function() {
      this.invalidStartDate = false;
    },
    "date_end.h1": function() {
      this.invalidEndDate = false;
    },
    "date_end.h2": function() {
      this.invalidEndDate = false;
    },
    "date_end.m1": function() {
      this.invalidEndDate = false;
    },
    "date_end.m2": function() {
      this.invalidEndDate = false;
    },
    gender_value: function() {
      this.invalidGender = false;
    },
    category_value: function() {
      this.invalidCategory = false;
    },
    "event.min_age": function() {
      this.invalidAge = false;
    },
    "event.max_age": function() {
      this.invalidAge = false;
    },
    "event.max_participant": function() {
      this.invalidParticipants = false;
    }
  },
  methods: {
    addTag(newTag) {
      const tag = {
        name: newTag,
        code: newTag.substring(0, 2) + Math.floor(Math.random() * 10000000)
      };
      this.options.push(tag);
      this.value.push(tag);
    },
    createdReturn() {
      this.$emit("clickCreate", false);
    },
    getRole() {
      let userData = decode(localStorage.getItem("user"));
      this.role = userData.role_id;
    },
    ClickCreate() {
      var reg = /^\d*\.?\d+$/;

      if (!this.event_pic) {
        this.invalidEvent_pic = true;
        this.alertEvent_pic = "required event picture";
      }
      if (!this.event.title) {
        this.invalidTitle = true;
        this.alertTitle = "required title";
      }
      if (!this.event.description) {
        this.invalidDescription = true;
        this.alertDescription = "required description";
      }
      if (!this.event.location) {
        this.invalidLocation = true;
        this.alertLocation = "required location";
      }
      if (
        !this.date_start.day ||
        !this.date_start.month ||
        !this.date_start.year
      ) {
        this.invalidStartDate = true;
        this.alertStartDate = "required start date";
      } else if (
        !this.date_start.h1 ||
        !this.date_start.h2 ||
        !this.date_start.m1 ||
        !this.date_start.m2
      ) {
        this.invalidStartDate = true;
        this.alertStartDate = "required start time";
      } else {
        this.validateStartDate();
      }
      if (!this.date_end.day || !this.date_end.month || !this.date_end.year) {
        this.invalidEndDate = true;
        this.alertEndDate = "required end date";
      } else if (
        !this.date_end.h1 ||
        !this.date_end.h2 ||
        !this.date_end.m1 ||
        !this.date_end.m2
      ) {
        this.invalidEndDate = true;
        this.alertEndDate = "required end time";
      } else {
        this.validateEndDate();
      }
      if (!this.gender_value.length) {
        this.invalidGender = true;
        this.alertGender = "required gender";
      }
      if (!this.category_value.length) {
        this.invalidCategory = true;
        this.alertCategory = "required category";
      }
      if (!this.event.min_age) {
        this.invalidAge = true;
        this.alertAge = "required min age";
      } else if (!this.event.max_age) {
        this.invalidAge = true;
        this.alertAge = "required max age";
      } else if (
        !reg.test(this.event.min_age) ||
        !reg.test(this.event.max_age)
      ) {
        this.invalidAge = true;
        this.alertAge = "must be only numbers";
      } else if (this.event.min_age < 13) {
        this.invalidAge = true;
        this.alertAge = "valid minimum age : 13";
      } else if (this.event.min_age >= this.event.max_age) {
        this.invalidAge = true;
        this.alertAge = "min must lower than max age";
      }
      if (!this.event.max_participant) {
        this.invalidParticipants = true;
        this.alertParticipants = "required max participants";
      } else if (!reg.test(this.event.max_participant)) {
        this.invalidParticipants = true;
        this.alertParticipants = "must be only numbers";
      } else if (this.event.max_participant < 2) {
        this.invalidParticipants = true;
        this.alertParticipants = "required at least 2 participants";
      } else {
        this.hs = this.date_start.h1 + this.date_start.h2;
        this.ms = this.date_start.m1 + this.date_start.m1;
        this.he = this.date_end.h1 + this.date_end.h2;
        this.me = this.date_end.m1 + this.date_end.m2;

        this.event.start_at = new Date(
          this.date_start.year +
            "-" +
            this.date_start.month +
            "-" +
            this.date_start.day +
            " " +
            this.hs +
            ":" +
            this.ms +
            ":00 GMT+0700"
        ).getTime();

        this.event.end_at = new Date(
          this.date_end.year +
            "-" +
            this.date_end.month +
            "-" +
            this.date_end.day +
            " " +
            this.he +
            ":" +
            this.me +
            ":00 GMT+0700"
        ).getTime();

        if (this.event.start_at <= new Date().getTime()) {
          this.invalidStartDate = true;
          this.alertStartDate = "must start after the current time";
        }
        if (this.event.end_at <= this.event.start_at) {
          this.invalidEndDate = true;
          this.alertEndDate = "end date must be after start date";
        }

        if (
          !this.invalidEvent_pic &&
          !this.invalidTitle &&
          !this.invalidDescription &&
          !this.invalidLocation &&
          !this.invalidStartDate &&
          !this.invalidEndDate &&
          !this.invalidGender &&
          !this.invalidCategory &&
          !this.invalidParticipants &&
          !this.invalidAge
        ) {
          this.gender_value.forEach((gender) => {
            this.genderList.push(gender.code);
          });

          this.category_value.forEach((category) => {
            this.categoryList.push(category.code);
          });
          EventService.create({
            event: this.event,
            gender_id: this.genderList,
            category_id: this.categoryList
          }).then(
            (res) => {
              if (res.event_id) {
                EventService.uploadEventPic(
                  this.event_pic.formData,
                  res.event_id
                ).then((res) => {
                  if (res) {
                    console.log(res);
                    if (this.role == "RO01") {
                      this.$router.push("/");
                    } else {
                      this.$emit("informationShow", true);
                    }
                  }
                });
              }
            },
            (error) => {
              console.log(error.message);
            }
          );
        }
      }
    },
    validateStartDate() {
      this.invalidStartDate = false;
      var reg = /^\d*\.?\d+$/;

      if (!reg.test(this.date_start.day)) {
        this.invalidStartDate = true;
        this.alertStartDate = "date must be only numbers";
      } else if (this.date_start.day < 1 || this.date_start.day > 31) {
        this.invalidStartDate = true;
        this.alertStartDate = "day must be only 1-31";
      } else if (
        (this.date_start.month == 4 && this.date_start.day > 30) ||
        (this.date_start.month == 6 && this.date_start.day > 30) ||
        (this.date_start.month == 9 && this.date_start.day > 30) ||
        (this.date_start.month == 11 && this.date_start.day > 30)
      ) {
        this.invalidStartDate = true;
        this.alertStartDate = "day or month is invalid";
      } else if (this.date_start.month == 2 && this.date_start.day > 29) {
        this.invalidStartDate = true;
        this.alertStartDate = "day or month is invalid";
      } else if (
        this.date_start.month == 2 &&
        this.date_start.day == 29 &&
        !(
          (0 == this.date_start.year % 4 && 0 != this.date_start.year % 100) ||
          0 == this.date_start.year % 400
        )
      ) {
        this.invalidStartDate = true;
        this.alertStartDate = "not a leap year";
      } else if (!reg.test(this.date_start.month)) {
        this.invalidStartDate = true;
        this.alertStartDate = "date must be only numbers";
      } else if (this.date_start.month < 1 || this.date_start.month > 12) {
        this.invalidStartDate = true;
        this.alertStartDate = "month must be only 1-12";
      } else if (!reg.test(this.date_start.year)) {
        this.invalidStartDate = true;
        this.alertStartDate = "date must be only numbers";
      } else if (this.date_start.year < 2021) {
        this.invalidStartDate = true;
        this.alertStartDate = "year must start at 2021";
      } else if (
        !reg.test(this.date_start.h1) ||
        !reg.test(this.date_start.h2) ||
        !reg.test(this.date_start.m1) ||
        !reg.test(this.date_start.m2)
      ) {
        this.invalidStartDate = true;
        this.alertStartDate = "time must be only numbers";
      } else if (
        (this.date_start.h1 == 2 && this.date_start.h2 > 3) ||
        this.date_start.h1 > 2
      ) {
        this.invalidStartDate = true;
        this.alertStartDate = "hour must be in 00-23";
      } else if (
        (this.date_start.m1 == 5 && this.date_start.m2 > 9) ||
        this.date_start.m1 > 5
      ) {
        this.invalidStartDate = true;
        this.alertStartDate = "minute must be in 00-59";
      }
    },
    validateEndDate() {
      this.invalidEndDate = false;
      var reg = /^\d*\.?\d+$/;

      if (!reg.test(this.date_end.day)) {
        this.invalidEndDate = true;
        this.alertEndDate = "date must be only numbers";
      } else if (this.date_end.day < 1 || this.date_end.day > 31) {
        this.invalidEndDate = true;
        this.alertEndDate = "day must be only 1-31";
      } else if (
        (this.date_end.month == 4 && this.date_end.day > 30) ||
        (this.date_end.month == 6 && this.date_end.day > 30) ||
        (this.date_end.month == 9 && this.date_end.day > 30) ||
        (this.date_end.month == 11 && this.date_end.day > 30)
      ) {
        this.invalidEndDate = true;
        this.alertEndDate = "day or month is invalid";
      } else if (this.date_end.month == 2 && this.date_end.day > 29) {
        this.invalidEndDate = true;
        this.alertEndDate = "day or month is invalid";
      } else if (
        this.date_end.month == 2 &&
        this.date_end.day == 29 &&
        !(
          (0 == this.date_end.year % 4 && 0 != this.date_end.year % 100) ||
          0 == this.date_end.year % 400
        )
      ) {
        this.invalidEndDate = true;
        this.alertEndDate = "not a leap year";
      } else if (!reg.test(this.date_end.month)) {
        this.invalidEndDate = true;
        this.alertEndDate = "date must be only numbers";
      } else if (this.date_end.month < 1 || this.date_end.month > 12) {
        this.invalidEndDate = true;
        this.alertEndDate = "month must be only 1-12";
      } else if (!reg.test(this.date_end.year)) {
        this.invalidEndDate = true;
        this.alertEndDate = "date must be only numbers";
      } else if (this.date_end.year < 2021) {
        this.invalidEndDate = true;
        this.alertEndDate = "year must start at 2021";
      } else if (
        !reg.test(this.date_end.h1) ||
        !reg.test(this.date_end.h2) ||
        !reg.test(this.date_end.m1) ||
        !reg.test(this.date_end.m2)
      ) {
        this.invalidEndDate = true;
        this.alertEndDate = "time must be only numbers";
      } else if (
        (this.date_end.h1 == 2 && this.date_end.h2 > 3) ||
        this.date_end.h1 > 2
      ) {
        this.invalidEndDate = true;
        this.alertEndDate = "hour must be in 00-23";
      } else if (
        (this.date_end.m1 == 5 && this.date_end.m2 > 9) ||
        this.date_end.m1 > 5
      ) {
        this.invalidEndDate = true;
        this.alertEndDate = "minute must be in 00-59";
      }
    }
  },
  mounted() {
    $(document).ready(function() {
      $("input").keyup(function() {
        if ($(this).val().length == $(this).attr("maxlength")) {
          const i = $("input").index(this);
          $("input")
            .eq(i + 1)
            .focus();
        }
      });
    });
  },
  created() {
    this.getRole();
    GenderService.getGenderList().then((res) => {
      if (res) {
        res.forEach((gender) => {
          let pick = new Pick("");
          pick.name = gender.gender_name;
          pick.code = gender.gender_id;
          this.gender_options.push(pick);
        });
      }
    });
    CategoryService.getCategoryList().then((res) => {
      if (res) {
        res.forEach((category) => {
          let pick = new Pick("");
          pick.name = category.category_name;
          pick.code = category.category_id;

          this.category_options.push(pick);
        });
      }
    });
  }
};
</script>

<style scoped>
#create-event-section {
  display: flex;
  justify-content: center;
}

#participant-section {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

#back_button_popup {
  color: #ff8864;
  font-size: 2.5em;
  font-family: "Atten-Round-New";
  text-align: center;
  width: 287px;
  padding: 9px 0px;
  background-color: #ffffff;
  border-radius: 35px;
  border: 2px solid #ff8864;
  margin-top: 70px;
  transition: 0.3s;
  margin-bottom: 30px;
  font-weight: 500;
}

#to {
  padding: 0px 5px;
}

.description {
  padding-bottom: 35px;
}

.pictureUpload {
  position: relative;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 420px;
  height: 165px;
  object-fit: cover;
  cursor: pointer;
}

.input_select {
  font-size: 1.75em;
  font-weight: 600;
  width: 100%;
  padding: 9px 12px 9px 15px;
  border: 2px solid #e3e3e3;
  border-radius: 10px;
  margin-bottom: 2px;
  box-shadow: none;
  font-family: "Atten-Round-New";
}

select {
  /* styling */
  background-color: white;
  border: thin solid #e3e3e3;
  border-radius: 4px;
  display: inline-block;
  font: inherit;
  line-height: 1.5em;
  padding: 0.5em 3.5em 0.5em 1em;

  /* reset */

  margin: 0;
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
  -webkit-appearance: none;
  -moz-appearance: none;
}

select.minimal {
  background-image: linear-gradient(45deg, transparent 50%, #e3e3e3 50%),
    linear-gradient(135deg, #e3e3e3 50%, transparent 50%);
  background-position: calc(100% - 20px) calc(1em + 2px),
    calc(100% - 15px) calc(1em + 2px), calc(100% - 2.5em) 0.5em;
  background-size: 5px 5px, 5px 5px, 1px 1.5em;
  background-repeat: no-repeat;
}

select.minimal:focus {
  background-image: linear-gradient(45deg, #e3e3e3 50%, transparent 50%),
    linear-gradient(135deg, transparent 50%, #e3e3e3 50%);
  background-position: calc(100% - 15px) 1em, calc(100% - 20px) 1em,
    calc(100% - 2.5em) 0.5em;
  background-size: 5px 5px, 5px 5px, 1px 1.5em;
  background-repeat: no-repeat;
  border-color: #e3e3e3;
  outline: 0;
}

select:-moz-focusring {
  color: transparent;
  text-shadow: 0 0 0 #000;
}

select:required:invalid {
  color: #cccccc;
}
select,
option {
  color: #444444;
}

.upload {
  color: #cccccc;
  font-size: 1.6em;
  font-weight: 500;
  margin: 0px 0px 0px 6px;
}

#addphoto {
  width: 25px;
}
#select-photo-section,
#select-photo-inside {
  border: 2px solid #e3e3e3;
  border-radius: 6px;
  padding: 3px 3px;
}

#select-photo-section {
  margin-top: 12px;
}

.date-section {
  width: 100%;
}

#select-photo-inside {
  margin-top: 60px;
  margin-bottom: 60px;
  cursor: pointer;
}

#right {
  margin-left: 30px;
}

#left {
  margin-right: 30px;
}

.input_textarea_box {
  font-size: 1.6em;
  font-weight: 500;
  color: #444444;
  padding: 7px 12px 7px 15px;
  border: 2px solid #e3e3e3;
  border-radius: 10px;
  margin-bottom: 2px;
  box-shadow: none;
  width: 400px;
  line-height: 21px;
}

.bio {
  padding-bottom: 31px;
}

@media screen and (max-width: 1024px) {
  #create-event-section {
    display: block;
  }

  #left,
  #right {
    margin: 0px;
  }

  .multiselect,
  .date-section,
  .time-section {
    width: 100% !important;
  }

  #participant-section {
    margin-top: 5px;
  }
}

@media screen and (max-width: 690px) {
  .input_box,
  .input_textarea_box {
    width: 250px !important;
  }

  .create_button,
  .back_button {
    width: 120px !important;
  }

  .pictureUpload {
    width: 268px !important;
    height: 125px;
  }

  #select-photo-inside {
    margin: 40px 0px;
  }
}

@media screen and (max-width: 490px) {
  .input_box,
  .input_textarea_box {
    width: 210px !important;
  }

  #participant-section {
    display: block;
  }

  .input_participant {
    width: calc(100% - 30px);
  }

  .input_age {
    width: 100%;
  }

  .create_button,
  .back_button {
    width: 110px !important;
  }

  .popup-form {
    padding: 0px 40px !important;
  }
}
</style>
