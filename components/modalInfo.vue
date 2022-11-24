<template>
  <!-- first model -->

  <div class="px-6 py-4">
    <div
      v-if="M1"
      class="fixed overflow-x-hidden overflow-y-auto inset-0 flex justify-center item-center z-50 top-0 right-0 left-0 p-4 w-full md:inset-0 md:h-full"
    >
      <div class="relative mx-auto w-auto max-w-2xl mt-5">
        <div class="bg-white w-full rounded shadow-2xl flex flex-col">
          <!-- <div class="text-2xl font-bold p-4"></div> -->
          <div
            class="flex justify-between items-start p-4 rounded-t border-b dark:border-gray-600"
          >
            <h3 class="text-xl font-semibold text-gray-900 dark:text-white">
              Please Enter your details
            </h3>
            <button
              type="button"
              class="text-gray-400 bg-transparent hover:bg-gray-200 hover:text-gray-900 rounded-lg text-sm p-1.5 ml-auto inline-flex items-center dark:hover:bg-gray-600 dark:hover:text-white"
              @click="M1 = false"
            >
              <svg
                aria-hidden="true"
                class="w-5 h-5"
                fill="currentColor"
                viewBox="0 0 20 20"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  fill-rule="evenodd"
                  d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z"
                  clip-rule="evenodd"
                ></path>
              </svg>
              <span class="sr-only">Close modal</span>
            </button>
          </div>

          <div class="p-6 space-y-6">
            <form action="">
              <div class="form-control w-full max-w-xs">
                <label class="label">
                  <span class="label-text">Enter your name</span>
                </label>
                <input
                  type="text"
                  v-model="name"
                  placeholder="Type here"
                  class="input input-bordered border-gray-400 w-full max-w-xs"
                  required
                />
              </div>

              <div class="form-control w-full max-w-xs">
                <label class="label">
                  <span class="label-text">Enter phone number</span>
                </label>
                <input
                  type="text"
                  v-model="phone"
                  placeholder="Type here"
                  class="input input-bordered border-gray-400 w-full max-w-xs"
                  required
                />
              </div>
            </form>
            <div
              class="flex justify-end w-full rounded-b border-t border-gray-200 dark:border-gray-600"
            >
              <div>
                <button
                  type="save"
                  class="btn btn-md my-2 mx-2 px-6 py-2 w-24"
                  @click="saveDetails"
                  @save.prevent="saveDetails"
                >
                  Save
                </button>
              </div>

              <div @click="saveDetails">
                <button
                  class="btn btn-md my-2 mx-2 px-6 py-2 w-24"
                  @click="(M1 = false) || (M2 = !M2)"
                >
                  Next
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div
      v-if="M1"
      class="absolute w-full md:inset-0 md:h-full z-40 opacity-25 bg-black"
    ></div>
  </div>

  <!-- second model -->
  <div class="px-6 py-4">
    <div
      v-if="M2"
      class="fixed overflow-x-hidden overflow-y-auto inset-0 flex justify-center item-center z-50 top-0 right-0 left-0 p-4 w-full md:inset-0 md:h-full"
    >
      <div class="relative mx-auto w-auto max-w-2xl mt-5">
        <div class="bg-white w-full rounded shadow-2xl flex flex-col">
          <!-- <div class="text-2xl font-bold p-4"></div> -->
          <div
            class="flex justify-between items-start p-4 rounded-t border-b dark:border-gray-600"
          >
            <h3 class="text-xl font-semibold text-gray-900 dark:text-white">
              Please Select Size
            </h3>
            <button
              type="button"
              class="text-gray-400 bg-transparent hover:bg-gray-200 hover:text-gray-900 rounded-lg text-sm p-1.5 ml-auto inline-flex items-center dark:hover:bg-gray-600 dark:hover:text-white"
              @click="M2 = false"
            >
              <svg
                aria-hidden="true"
                class="w-5 h-5"
                fill="currentColor"
                viewBox="0 0 20 20"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  fill-rule="evenodd"
                  d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z"
                  clip-rule="evenodd"
                ></path>
              </svg>
              <span class="sr-only">Close modal</span>
            </button>
          </div>

          <div class="p-6 space-y-6">
            <form action="">
              <select
                v-model="select"
                class="select select-bordered w-full max-w-xs"
              >
                <option disabled value="">Select size</option>
                <option>XS</option>
                <option>S</option>
                <option>M</option>
                <option>L</option>
                <option>XL</option>
                <option>2XL</option>
                <option>3XL</option>
                <option>4Xl</option>
              </select>
            </form>

            <!-- <button
              class="btn-md font-semibold hover:bg-success hover:text-white box-border border-2 border-gray-600 rounded py-1 px-3 mx-2"
            >
              S
            </button>
            <button
              class="btn-md font-semibold hover:bg-success hover:text-white box-border border-2 border-gray-600 rounded py-1 px-3 mx-2"
            >
              M
            </button>
            <button
              class="btn-md font-semibold hover:bg-success hover:text-white box-border border-2 border-gray-600 rounded py-1 px-3 mx-2"
            >
              L
            </button>
            <button
              class="btn-md font-semibold hover:bg-success hover:text-white box-border border-2 border-gray-600 rounded py-1 px-3 mx-2"
            >
              XL
            </button>
            <button
              class="btn-md font-semibold hover:bg-success hover:text-white box-border border-2 border-gray-600 rounded py-1 px-3 mx-2"
            >
              2XL
            </button>
            <button
              class="btn-md font-semibold hover:bg-success hover:text-white box-border border-2 border-gray-600 rounded py-1 px-3 mx-2"
            >
              3XL
            </button>
            <button
              class="btn-md font-semibold hover:bg-success hover:text-white box-border border-2 border-gray-600 rounded py-1 px-3 mx-2"
            >
              4XL
            </button> -->

            <div
              class="flex justify-end w-full rounded-b border-t border-gray-200 dark:border-gray-600"
            >
              <div>
                <button
                  type="save"
                  class="btn btn-md my-2 mx-2 px-6 py-2 w-24"
                  @click="selectSize"
                  @save.prevent="selectSize"
                >
                  Save
                </button>
              </div>
              <div @click="selectSize">
                <button
                  class="btn btn-md my-2 mx-2 px-6 py-2 w-24"
                  @click="(M2 = false) || (M3 = !M3)"
                >
                  Next
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div
      v-if="M2"
      class="absolute w-full md:inset-0 md:h-full z-40 opacity-25 bg-black"
    ></div>
  </div>

  <!-- third modal -->

  <div class="px-6 py-4">
    <div
      v-if="M3"
      class="fixed overflow-x-hidden overflow-y-auto inset-0 flex justify-center item-center z-50 top-0 right-0 left-0 p-4 w-full md:inset-0 md:h-full"
    >
      <div class="relative mx-auto w-auto max-w-2xl mt-5">
        <div class="bg-white w-full rounded shadow-2xl flex flex-col">
          <!-- <div class="text-2xl font-bold p-4"></div> -->
          <div
            class="flex justify-between items-start p-4 rounded-t border-b dark:border-gray-600"
          >
            <h3 class="text-xl font-semibold text-gray-900 dark:text-white">
              Billing Address
            </h3>
            <button
              type="button"
              class="text-gray-400 bg-transparent hover:bg-gray-200 hover:text-gray-900 rounded-lg text-sm p-1.5 ml-auto inline-flex items-center dark:hover:bg-gray-600 dark:hover:text-white"
              @click="M3 = false"
            >
              <svg
                aria-hidden="true"
                class="w-5 h-5"
                fill="currentColor"
                viewBox="0 0 20 20"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  fill-rule="evenodd"
                  d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z"
                  clip-rule="evenodd"
                ></path>
              </svg>
              <span class="sr-only">Close modal</span>
            </button>
          </div>

          <div class="p-6 space-y-6">
            <form action="">
              <div class="form-control">
                <label class="label">
                  <span class="label-text">Your billing address</span>
                </label>
                <textarea
                  v-model="address"
                  class="textarea textarea-bordered h-24"
                  placeholder="Bio"
                ></textarea>
              </div>
            </form>

            <div
              class="flex justify-end w-full rounded-b border-t border-gray-200 dark:border-gray-600"
            >
              <div>
                <button
                  type="save"
                  class="btn btn-md my-2 mx-2 px-6 py-2 w-24"
                  @click="showAddress"
                  @save.prevent="showAddress"
                >
                  Save
                </button>
              </div>
              <div>
                <button
                  class="btn btn-md my-2 mx-2 px-6 py-2 w-24"
                  @click="M3 = false"
                >
                  Thank You
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div
      v-if="M3"
      class="absolute w-full md:inset-0 md:h-full z-40 opacity-25 bg-black"
    ></div>
  </div>
</template>
<script setup>
// define M1 props
const { M1 } = defineProps(["M1"]);
const M2 = ref(false);
const M3 = ref(false);
const name = ref("");
const phone = ref("");
const select = ref("");
const address = ref("");
const saveDetails = () => {
  console.log(name.value);
  console.log(phone.value);
};
const selectSize = () => {
  console.log(select.value);
};
const showAddress = () => {
  console.log(address.value);
};
</script>
