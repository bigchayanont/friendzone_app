<template>
  <div>
    <div v-if="Case">
      <div id="category-section">
        <div id="left">
          <!-- Input -->
          <div>
            <h2 class="input_title">Select Category to edit</h2>
            <h2 v-show="invalidSelectChange" class="input_title">
              <span class="orange-color"> * {{ alertSelectChange }}</span>
            </h2>
            <select
              name="gender"
              class="input_select minimal"
              v-model="selected"
              required
            >
              <option value="" disabled selected hidden>select category</option>
              <option
                v-for="(category, index) in categoryList"
                :key="index"
                :value="category"
              >
                {{ categoryList[index].category_name }}
              </option>
            </select>
          </div>
          <!-- Input -->
          <div id="result" class="section">
            <div>
              <h1 v-if="!selected" id="no-info">No Information</h1>
              <div v-if="selected">
                <!-- not change -->
                <TypeBox
                  v-if="
                    !newNameCategory && !newColorCategory && !newIconCategory
                  "
                  :admin="true"
                  :nameCategory="selected.category_name"
                  :icon="selected.icon_white"
                  :colorCode="selected.color_code"
                  :bgcolorCode="selected.color_code"
                  id="typebox"
                />
                <div
                  v-if="
                    !newNameCategory && !newColorCategory && !newIconCategory
                  "
                  style="margin-top: 15px"
                >
                  <TypeBox
                    :admin="true"
                    :nameCategory="selected.category_name"
                    :icon="selected.icon_black"
                    :colorCode="GreyColor"
                    :bgcolorCode="WhiteColor"
                    id="typebox-dark"
                  />
                </div>
                <!-- not change -->
                <!-- change Name Only -->
                <TypeBox
                  v-if="
                    newNameCategory && !newColorCategory && !newIconCategory
                  "
                  :admin="true"
                  :nameCategory="changeName"
                  :icon="selected.icon_white"
                  :colorCode="selected.color_code"
                  :bgcolorCode="selected.color_code"
                  id="typebox"
                />
                <div
                  v-if="
                    newNameCategory && !newColorCategory && !newIconCategory
                  "
                  style="margin-top: 15px"
                >
                  <TypeBox
                    :admin="true"
                    :nameCategory="changeName"
                    :icon="selected.icon_black"
                    :colorCode="GreyColor"
                    :bgcolorCode="WhiteColor"
                    id="typebox-dark"
                  />
                </div>
                <!-- change Name Only -->
                <!-- change Color Only -->
                <TypeBox
                  v-if="
                    newColorCategory && !newNameCategory && !newIconCategory
                  "
                  :admin="true"
                  :nameCategory="selected.category_name"
                  :icon="selected.icon_white"
                  :colorCode="changeColor"
                  :bgcolorCode="changeColor"
                  id="typebox"
                />
                <div
                  v-if="
                    newColorCategory && !newNameCategory && !newIconCategory
                  "
                  style="margin-top: 15px"
                >
                  <TypeBox
                    :admin="true"
                    :nameCategory="selected.category_name"
                    :icon="selected.icon_black"
                    :colorCode="GreyColor"
                    :bgcolorCode="WhiteColor"
                    id="typebox-dark"
                  />
                </div>
                <!-- change Color Only -->
                <!-- change Icon Only -->
                <TypeBox
                  v-if="
                    newIconCategory && !newNameCategory && !newColorCategory
                  "
                  :admin="true"
                  :nameCategory="selected.category_name"
                  :icon="changeIconWhite"
                  :colorCode="selected.color_code"
                  :bgcolorCode="selected.color_code"
                  id="typebox"
                />
                <div
                  v-if="
                    newIconCategory && !newNameCategory && !newColorCategory
                  "
                  style="margin-top: 15px"
                >
                  <TypeBox
                    :admin="true"
                    :nameCategory="selected.category_name"
                    :icon="changeIconBlack"
                    :colorCode="GreyColor"
                    :bgcolorCode="WhiteColor"
                    id="typebox-dark"
                  />
                </div>
                <!-- change Icon Only -->
                <!-- change name and Color -->
                <TypeBox
                  v-if="newColorCategory && newNameCategory && !newIconCategory"
                  :admin="true"
                  :nameCategory="changeName"
                  :icon="selected.icon_white"
                  :colorCode="changeColor"
                  :bgcolorCode="changeColor"
                  id="typebox"
                />
                <div
                  v-if="newColorCategory && newNameCategory && !newIconCategory"
                  style="margin-top: 15px"
                >
                  <TypeBox
                    :admin="true"
                    :nameCategory="changeName"
                    :icon="selected.icon_black"
                    :colorCode="GreyColor"
                    :bgcolorCode="WhiteColor"
                    id="typebox-dark"
                  />
                </div>
                <!-- change name and Color -->
                <!-- change name and Icon -->
                <TypeBox
                  v-if="!newColorCategory && newNameCategory && newIconCategory"
                  :admin="true"
                  :nameCategory="changeName"
                  :icon="changeIconWhite"
                  :colorCode="selected.color_code"
                  :bgcolorCode="selected.color_code"
                  id="typebox"
                />
                <div
                  v-if="!newColorCategory && newNameCategory && newIconCategory"
                  style="margin-top: 15px"
                >
                  <TypeBox
                    :admin="true"
                    :nameCategory="changeName"
                    :icon="changeIconBlack"
                    :colorCode="GreyColor"
                    :bgcolorCode="WhiteColor"
                    id="typebox-dark"
                  />
                </div>
                <!-- change name and Icon -->
                <!-- change color and Icon -->
                <TypeBox
                  v-if="newColorCategory && !newNameCategory && newIconCategory"
                  :admin="true"
                  :nameCategory="selected.category_name"
                  :icon="changeIconWhite"
                  :colorCode="changeColor"
                  :bgcolorCode="changeColor"
                  id="typebox"
                />
                <div
                  v-if="newColorCategory && !newNameCategory && newIconCategory"
                  style="margin-top: 15px"
                >
                  <TypeBox
                    :admin="true"
                    :nameCategory="selected.category_name"
                    :icon="changeIconBlack"
                    :colorCode="GreyColor"
                    :bgcolorCode="WhiteColor"
                    id="typebox-dark"
                  />
                </div>
                <!-- change color and Icon -->
                <!-- change All -->
                <TypeBox
                  v-if="newColorCategory && newNameCategory && newIconCategory"
                  :admin="true"
                  :nameCategory="changeName"
                  :icon="changeIconWhite"
                  :colorCode="changeColor"
                  :bgcolorCode="changeColor"
                  id="typebox"
                />
                <div
                  v-if="newColorCategory && newNameCategory && newIconCategory"
                  style="margin-top: 15px"
                >
                  <TypeBox
                    :admin="true"
                    :nameCategory="changeName"
                    :icon="changeIconBlack"
                    :colorCode="GreyColor"
                    :bgcolorCode="WhiteColor"
                    id="typebox-dark"
                  />
                </div>
                <!-- change All -->
              </div>
            </div>
          </div>
        </div>
        <div id="right">
          <!-- Input -->
          <div>
            <div class="input_inline">
              <h2 class="input_title">Rename Category</h2>
              <h2 v-show="invalidNameChange" class="input_title">
                <span class="orange-color"> * {{ alertNameChange }}</span>
              </h2>
            </div>
            <div class="button-section">
              <input
                class="input_box"
                type="text"
                maxlength="64"
                size="64"
                placeholder="enter new category name"
                v-model="newName"
              />
              <div class="button">
                <button @click="renameCategory()">Rename</button>
              </div>
            </div>
          </div>
          <!-- Input -->

          <!-- Input -->
          <div>
            <div class="input_inline">
              <h2 class="input_title">Change Color</h2>
              <h2 v-show="invalidColorChange" class="input_title">
                <span class="orange-color"> * {{ alertColorChange }}</span>
              </h2>
            </div>
            <div class="button-section">
              <input
                class="input_box"
                type="text"
                maxlength="7"
                size="7"
                placeholder="enter new category color"
                v-model="newColor"
              />
              <div class="button">
                <button @click="reColorCategory()">Change</button>
              </div>
            </div>
          </div>
          <!-- Input -->

          <!-- Input -->
          <div>
            <div class="input_inline">
              <h2 class="input_title">Change Category Icon</h2>
              <h2 v-show="invalidIconChange" class="input_title">
                <span class="orange-color"> * {{ alertIconChange }}</span>
              </h2>
            </div>
            <div class="button-section">
              <Upload v-model="newIconWhite">
                <div slot="activator" class="select-photo-inside">
                  <img
                    id="addphoto"
                    src="@/assets/icon/icons8-add-image-96.png"
                  />
                  <h1 v-if="!newIconWhite" class="upload">upload white icon</h1>
                  <h1 v-if="newIconWhite" class="upload">uploaded</h1>
                </div>
              </Upload>
            </div>
            <div style="margin-top: 10px" class="button-section">
              <Upload v-model="newIconBlack">
                <div slot="activator" class="select-photo-inside">
                  <img
                    id="addphoto"
                    src="@/assets/icon/icons8-add-image-96.png"
                  />
                  <h1 v-if="!newIconBlack" class="upload">upload dark icon</h1>
                  <h1 v-if="newIconBlack" class="upload">uploaded</h1>
                </div>
              </Upload>
              <div class="button">
                <button @click="reIcon()">Change</button>
              </div>
            </div>
          </div>
          <!-- Input -->
          <h2 v-show="invalidChange" class="input_title">
                <span class="orange-color"> * {{ alertChange }}</span>
              </h2>
          <!-- Input -->
          <!-- <div id="delete">
            <div class="button-section">
              <h2 class="input_title">Want to delete this category?</h2>
              <div class="button">
                <button @click="clickInterest()">Delete</button>
              </div>
            </div>
          </div> -->
          <!-- Input -->
        </div>
      </div>
      <div class="button-section">
        <button class="back_button" @click="cancel()">Cancel</button>
        <button class="create_button" @click="update()">Save</button>
      </div>
    </div>
    <div v-if="!Case">
      <div id="category-section">
        <div id="left">
          <div id="result-add" class="section">
            <div>
              <!-- not change -->
              <TypeBox
                v-if="!nameAdd && !colorAdd && !iconAdd"
                :nameCategory="defaultName"
                :icon="categoryList[1].icon_white"
                :colorCode="defaultColor"
                :bgcolorCode="defaultColor"
                id="typebox"
              />
              <div
                v-if="!nameAdd && !colorAdd && !iconAdd"
                style="margin-top: 15px"
              >
                <TypeBox
                  :nameCategory="defaultName"
                  :icon="categoryList[1].icon_black"
                  :colorCode="GreyColor"
                  :bgcolorCode="WhiteColor"
                  id="typebox-dark"
                />
              </div>
              <!-- not change -->
              <!-- change Name Only -->
              <TypeBox
                v-if="nameAdd && !colorAdd && !iconAdd"
                :nameCategory="addNewName"
                :icon="categoryList[1].icon_white"
                :colorCode="defaultColor"
                :bgcolorCode="defaultColor"
                id="typebox"
              />
              <div
                v-if="nameAdd && !colorAdd && !iconAdd"
                style="margin-top: 15px"
              >
                <TypeBox
                  :nameCategory="addNewName"
                  :icon="categoryList[1].icon_black"
                  :colorCode="GreyColor"
                  :bgcolorCode="WhiteColor"
                  id="typebox-dark"
                />
              </div>
              <!-- change Name Only -->
              <!-- change Color Only -->
              <TypeBox
                v-if="colorAdd && !nameAdd && !iconAdd"
                :nameCategory="defaultName"
                :icon="categoryList[1].icon_white"
                :colorCode="addNewColor"
                :bgcolorCode="addNewColor"
                id="typebox"
              />
              <div
                v-if="colorAdd && !nameAdd && !iconAdd"
                style="margin-top: 15px"
              >
                <TypeBox
                  :nameCategory="defaultName"
                  :icon="categoryList[1].icon_black"
                  :colorCode="GreyColor"
                  :bgcolorCode="WhiteColor"
                  id="typebox-dark"
                />
              </div>
              <!-- change Color Only -->
              <!-- change Icon Only -->
              <TypeBox
                v-if="iconAdd && !nameAdd && !colorAdd"
                :nameCategory="defaultName"
                :icon="addNewIconWhite"
                :colorCode="defaultColor"
                :bgcolorCode="defaultColor"
                id="typebox"
              />
              <div
                v-if="iconAdd && !nameAdd && !colorAdd"
                style="margin-top: 15px"
              >
                <TypeBox
                  :nameCategory="defaultName"
                  :icon="addNewIconBlack"
                  :colorCode="GreyColor"
                  :bgcolorCode="WhiteColor"
                  id="typebox-dark"
                />
              </div>
              <!-- change Icon Only -->
              <!-- change name and Color -->
              <TypeBox
                v-if="colorAdd && nameAdd && !iconAdd"
                :nameCategory="addNewName"
                :icon="categoryList[1].icon_white"
                :colorCode="addNewColor"
                :bgcolorCode="addNewColor"
                id="typebox"
              />
              <div
                v-if="colorAdd && nameAdd && !iconAdd"
                style="margin-top: 15px"
              >
                <TypeBox
                  :nameCategory="addNewName"
                  :icon="categoryList[1].icon_black"
                  :colorCode="GreyColor"
                  :bgcolorCode="WhiteColor"
                  id="typebox-dark"
                />
              </div>
              <!-- change name and Color -->
              <!-- change name and Icon -->
              <TypeBox
                v-if="!colorAdd && nameAdd && iconAdd"
                :nameCategory="addNewName"
                :icon="addNewIconWhite"
                :colorCode="defaultColor"
                :bgcolorCode="defaultColor"
                id="typebox"
              />
              <div
                v-if="!colorAdd && nameAdd && iconAdd"
                style="margin-top: 15px"
              >
                <TypeBox
                  :nameCategory="addNewName"
                  :icon="addNewIconBlack"
                  :colorCode="GreyColor"
                  :bgcolorCode="WhiteColor"
                  id="typebox-dark"
                />
              </div>
              <!-- change name and Icon -->
              <!-- change color and Icon -->
              <TypeBox
                v-if="colorAdd && !nameAdd && iconAdd"
                :nameCategory="defaultName"
                :icon="addNewIconWhite"
                :colorCode="addNewColor"
                :bgcolorCode="addNewColor"
                id="typebox"
              />
              <div
                v-if="colorAdd && !nameAdd && iconAdd"
                style="margin-top: 15px"
              >
                <TypeBox
                  :nameCategory="defaultName"
                  :icon="addNewIconBlack"
                  :colorCode="GreyColor"
                  :bgcolorCode="WhiteColor"
                  id="typebox-dark"
                />
              </div>
              <!-- change color and Icon -->
              <!-- change All -->
              <TypeBox
                v-if="colorAdd && nameAdd && iconAdd"
                :nameCategory="addNewName"
                :icon="addNewIconWhite"
                :colorCode="addNewColor"
                :bgcolorCode="addNewColor"
                id="typebox"
              />
              <div
                v-if="colorAdd && nameAdd && iconAdd"
                style="margin-top: 15px"
              >
                <TypeBox
                  :nameCategory="addNewName"
                  :icon="addNewIconBlack"
                  :colorCode="GreyColor"
                  :bgcolorCode="WhiteColor"
                  id="typebox-dark"
                />
              </div>
              <!-- change All -->
            </div>
          </div>
        </div>
        <div id="right">
          <!-- Input -->
          <div>
            <div class="input_inline">
              <h2 class="input_title">Add Name Category</h2>
              <h2 v-show="invalidNameAdd" class="input_title">
                <span class="orange-color"> * {{ alertNameAdd }}</span>
              </h2>
            </div>
            <div class="button-section">
              <input
                class="input_box"
                type="text"
                maxlength="64"
                size="64"
                placeholder="enter new category name"
                v-model="addNewName"
              />
              <div class="button">
                <button @click="addNameCategory()">ADD</button>
              </div>
            </div>
          </div>
          <!-- Input -->

          <!-- Input -->
          <div>
            <div class="input_inline">
              <h2 class="input_title">Add Color</h2>
              <h2 v-show="invalidColorAdd" class="input_title">
                <span class="orange-color"> * {{ alertColorAdd }}</span>
              </h2>
            </div>
            <div class="button-section">
              <input
                class="input_box"
                type="text"
                maxlength="7"
                size="7"
                placeholder="enter new category color"
                v-model="addNewColor"
              />
              <div class="button">
                <button @click="addColorCategory()">ADD</button>
              </div>
            </div>
          </div>
          <!-- Input -->

          <!-- Input -->
          <div>
            <div class="input_inline">
              <h2 class="input_title">Add Category Icon</h2>
              <h2 v-show="invalidIconAdd" class="input_title">
                <span class="orange-color"> * {{ alertIconAdd }}</span>
              </h2>
            </div>
            <div class="button-section">
              <Upload v-model="addIconWhite">
                <div slot="activator" class="select-photo-inside">
                  <img
                    id="addphoto"
                    src="@/assets/icon/icons8-add-image-96.png"
                  />
                  <h1 v-if="!addIconWhite" class="upload">upload white icon</h1>
                  <h1 v-if="addIconWhite" class="upload">uploaded</h1>
                </div>
              </Upload>
            </div>
            <div style="margin-top: 10px" class="button-section">
              <Upload v-model="addIconBlack">
                <div slot="activator" class="select-photo-inside">
                  <img
                    id="addphoto"
                    src="@/assets/icon/icons8-add-image-96.png"
                  />
                  <h1 v-if="!addIconBlack" class="upload">upload dark icon</h1>
                  <h1 v-if="addIconBlack" class="upload">uploaded</h1>
                </div>
              </Upload>
              <div class="button">
                <button @click="addIcon()">ADD</button>
              </div>
            </div>
          </div>
          <!-- Input -->
        </div>
      </div>
      <div class="button-section">
        <button class="back_button" @click="cancel()">Cancel</button>
        <button class="create_button" @click="save()">Save</button>
      </div>
    </div>
  </div>
</template>

<script>
import CategoryService from "../../../services/category.service";
import TypeBox from "@/components/category/TypeBox.vue";
import Upload from "@/components/UploadPic.vue";

export default {
  props: ["Case"],
  data() {
    return {
      categoryList: null,
      newIconWhite: "",
      newIconBlack: "",
      changeIconWhite: "",
      changeIconBlack: "",
      selected: "",
      newName: "",
      newColor: "",
      changeName: "",
      changeColor: "",
      newNameCategory: false,
      newColorCategory: false,
      newIconCategory: false,
      GreyColor: "#A0A0A0 !important",
      WhiteColor: "#FFFFFF",
      nameAdd: false,
      colorAdd: false,
      iconAdd: false,
      addNewName: "",
      addNewColor: "",
      addNewIconWhite: "",
      addNewIconBlack: "",
      addIconWhite: "",
      addIconBlack: "",
      defaultName: "Add name",
      defaultColor: "#f11111",
      defaultIcon: "@/assets/icon/coin.png",
      invalidSelectChange: false,
      invalidNameChange: false,
      invalidNameAdd: false,
      invalidColorChange: false,
      invalidColorAdd: false,
      invalidIconChange: false,
      invalidIconAdd: false,
      invalidChange: false,
      alertSelectChange: "",
      alertNameChange: "",
      alertNameAdd: "",
      alertColorChange: "",
      alertColorAdd: "",
      alertIconChange: "",
      alertIconAdd: "",
      alertChange: "",
      isWhiteUpload: false,
      isBlackUpload: false
    };
  },
  watch: {
    selected: function() {
      this.newNameCategory = false;
      this.newColorCategory = false;
      this.newIconCategory = false;
      this.newName = null;
      this.newColor = null;
      this.newIconWhite = "";
      this.newIconBlack = "";
      this.changeIconWhite = null;
      this.changeIconBlack = null;
      this.newIconWhite.imageURL = null;
      this.newIconBlack.imageURL = null;
    },
    addNewName: function() {
      if (!this.addNewName) {
        this.nameAdd = false;
      }
    },
    addNewColor: function() {
      if (!this.addNewColor) {
        this.colorAdd = false;
      }
    }
  },
  components: {
    TypeBox,
    Upload
  },
  created() {
    CategoryService.getCategoryList().then((res) => {
      if (res) {
        this.categoryList = res;
      }
    });
  },
  methods: {
    cancel() {
      this.$emit("cancel", false);
    },
    renameCategory() {
      this.changeName = this.newName;
      this.newNameCategory = true;
    },
    reColorCategory() {
      this.changeColor = this.newColor;
      this.newColorCategory = true;
    },
    reIcon() {
      this.changeIconWhite = this.newIconWhite.imageURL;
      this.changeIconBlack = this.newIconBlack.imageURL;
      this.newIconCategory = true;
    },
    addNameCategory() {
      if (this.addNewName) this.nameAdd = true;
    },
    addColorCategory() {
      if (this.addNewColor) this.colorAdd = true;
    },
    addIcon() {
      this.iconAdd = true;
      this.addNewIconWhite = this.addIconWhite.imageURL;
      this.addNewIconBlack = this.addIconBlack.imageURL;
    },
    save() {
      if (
        this.addNewName &&
        this.addNewColor &&
        this.addIconWhite.formData &&
        this.addIconBlack.formData
      ) {
        CategoryService.create({
          category_name: this.addNewName,
          color_code: this.addNewColor
        }).then(async (res) => {
          if (res) {
            await CategoryService.uploadCategoryIcon(
              this.addIconWhite.formData,
              res.category_id,
              "white"
            ).then((res) => {
              console.log(res);
              this.isWhiteUpload = true;
            });

            await CategoryService.uploadCategoryIcon(
              this.addIconBlack.formData,
              res.category_id,
              "black"
            ).then((res) => {
              console.log(res);
              this.isBlackUpload = true;
            });

            if (this.isWhiteUpload && this.isBlackUpload) {
              window.location.href = "/admin";
            }
          }
        });
      } else {
        if (!this.addNewName) {
          this.invalidNameAdd = true;
          this.alertNameAdd = "required category name";
        }
        if (!this.addNewColor) {
          this.invalidColorAdd = true;
          this.alertColorAdd = "required color code";
        }
        if (!this.addIconWhite.formData && !this.addIconBlack.formData) {
          this.invalidIconAdd = true;
          this.alertIconAdd = "required icon";
        } else if (!this.addIconWhite.formData) {
          this.invalidIconAdd = true;
          this.alertIconAdd = "required white icon";
        } else if (!this.addIconBlack.formData) {
          this.invalidIconAdd = true;
          this.alertIconAdd = "required dark icon";
        }
      }
    },
    async update() {
      if (this.selected) {
        if (
          this.newName ||
          this.newColor ||
          this.newIconWhite.formData ||
          this.newIconBlack.formData
        ) {
          if (this.newName || this.newColor) {
            let category = {
              category_id: this.selected.category_id,
              category_name: this.newName,
              color_code: this.newColor
            };

            if (!this.newName) {
              delete category.category_name;
            }
            if (!this.newColor) {
              delete category.color_code;
            }

            await CategoryService.update(category).then((res) => {
              if (res) {
                console.log(res);
              }
            });
          }

          if (this.newIconWhite.formData) {
            await CategoryService.uploadCategoryIcon(
              this.newIconWhite.formData,
              this.selected.category_id,
              "white"
            ).then((res) => {
              console.log(res);
            });
          }

          if (this.newIconBlack.formData) {
            await CategoryService.uploadCategoryIcon(
              this.newIconBlack.formData,
              this.selected.category_id,
              "black"
            ).then((res) => {
              console.log(res);
            });
          }

          await this.$emit("exitClick", false);
        } else {
          this.invalidChange = true;
          this.alertChange = "nothing to change";
        }
      } else {
        this.invalidSelectChange = true;
        this.alertSelectChange = "required category to edit";
      }
    }
  }
};
</script>

<style scoped>
#category-section {
  display: flex;
  justify-content: space-between;
  margin-top: 10px;
}

#left {
  margin-right: 10px;
}

#right {
  margin-left: 10px;
}

.input_inline {
  display: flex;
  align-items: center;
}

.input_inline > h2:nth-child(2) {
  padding-left: 10px;
}

.input_box {
  width: 200px !important;
}

.input_select {
  font-size: 1.6em;
  font-weight: 450;
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

#result {
  border: 1.75px solid #444444;
  border-radius: 10px;
  margin-top: 15px;
  padding: 8px 0px;
  width: 350px;
  height: 200px;
}

#result-add {
  border: 1.75px solid #444444;
  border-radius: 10px;
  margin-top: 15px;
  padding: 8px 0px;
  width: 350px;
  height: 220px;
}

#typebox,
#typebox-dark {
  margin: 0px !important;
  padding: 5px !important;
}

#typebox {
  border: 1.75px solid #cccccc;
}

#typebox-dark {
  border: 2px solid #ff8864;
}

#no-info {
  font-size: 1.85em;
  color: #444444;
  text-transform: uppercase;
  text-align: center;
}

.button {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-left: 15px;
}

.button > button {
  background-color: #ffffff;
  font-family: "Atten-Round-New";
  text-transform: uppercase;
  font-size: 1.25em;
  font-weight: 600;
  width: 80px;
  margin: 0px;
  color: #ff8864;
  border: 2px solid #ff8864;
  border-radius: 16px;
  padding: 5px 18px;
}

.button-section {
  display: flex;
  align-items: center;
}

.select-photo-inside {
  cursor: pointer;
  border: 2px solid #e3e3e3;
  border-radius: 10px;
  padding: 5px 5px 5px 12px;
  display: flex;
  align-items: center;
  width: 217px;
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

#delete {
  margin-top: 15px;
}

@media screen and (min-width: 1920px) {
  #result,
  #result-add {
    width: 500px;
  }
}

@media screen and (max-width: 1024px) {
  #category-section {
    display: block;
  }

  #left,
  #right {
    margin: 0px;
  }

  .input_box {
    width: 100% !important;
  }

  .select-photo-inside {
    width: 400px;
  }

  #result,
  #result-add {
    width: 100%;
    height: 145px;
    margin-bottom: 20px;
  }
}

@media screen and (max-width: 690px) {
  .input_box,
  .input_textarea_box {
    width: 160px !important;
  }

  .select-photo-inside {
    width: 170px;
  }

  .create_button,
  .back_button {
    width: 120px !important;
  }
}

@media screen and (max-width: 490px) {
  .create_button,
  .back_button {
    width: 110px !important;
  }

  .input_box,
  .input_textarea_box {
    width: 130px !important;
  }

  .select-photo-inside {
    width: 140px;
  }

  .popup-form {
    padding: 0px 40px !important;
  }
}
</style>
