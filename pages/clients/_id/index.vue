<template>
  <div class="flex space-x-3">
    <div class="w-9/12">
      <div
        class="
          h-24
          w-full
          relative
          mt-4
          rounded-md
          bg-blue-900
          px-4
          py-2
          flex
          items-center
          space-x-8
        "
      >
        <div>
          <img src="/../profile.png" alt="" class="h-20 w-20 rounded-full" />
        </div>
        <div>
          <h3 class="text-xl text-white font-semibold">Nom du client</h3>
          <h3 class="text-gray-100">Phone du client</h3>
        </div>
        <div class="absolute right-3">
          <nuxt-link
            to="/clients"
            class="text-white px-8 py-2 rounded-md bg-blue-500"
          >
            retour
          </nuxt-link>
        </div>
      </div>
      <div class="bg-white flex flex-col justify-center">
        <table class="min-w-full divide-y divide-gray-200">
          <thead class="bg-gray-100">
            <tr>
              <th
                scope="col"
                class="
                  px-6
                  py-2
                  text-left text-xs
                  font-medium
                  text-gray-500
                  uppercase
                  tracking-wider
                "
              >
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  class="h-6 w-6"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke="currentColor"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M7 20l4-16m2 16l4-16M6 9h14M4 15h14"
                  />
                </svg>
              </th>
              <th
                scope="col"
                class="
                  px-6
                  py-2
                  text-left text-xs
                  font-medium
                  text-gray-500
                  uppercase
                  tracking-wider
                "
              >
                Operation
              </th>
              <th
                scope="col"
                class="
                  px-6
                  py-2
                  text-center text-xs
                  font-medium
                  text-gray-500
                  uppercase
                  tracking-wider
                "
              >
                Montant( $ )
              </th>
              <th
                scope="col"
                class="
                  px-6
                  py-2
                  text-center text-xs
                  font-medium
                  text-gray-500
                  uppercase
                  tracking-wider
                "
              >
                Compte
              </th>
              <th
                scope="col"
                class="
                  px-6
                  py-2
                  text-center text-xs
                  font-medium
                  text-gray-500
                  uppercase
                  tracking-wider
                "
              >
                Garantie
              </th>
              <th
                scope="col"
                class="
                  px-6
                  py-2
                  text-center text-xs
                  font-medium
                  text-gray-500
                  uppercase
                  tracking-wider
                "
              >
                Date
              </th>
              <th
                scope="col"
                class="
                  px-6
                  py-2
                  text-center text-xs
                  font-medium
                  text-gray-500
                  uppercase
                  tracking-wider
                "
              >
                Actions
              </th>
            </tr>
          </thead>
          <tbody class="bg-white divide-y divide-gray-200">
            <payment-item v-for="(n, i) in payments" :item="n" :key="i" />
          </tbody>
        </table>
      </div>
    </div>
    <div class="w-3/12 mt-4 space-y-4">
      <div
        class="
          h-24
          flex
          text-white
          font-semibold
          items-center
          space-x-4
          justify-center
          rounded
          bg-blue-900
        "
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-6 w-6"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M8 10h.01M12 10h.01M16 10h.01M9 16H5a2 2 0 01-2-2V6a2 2 0 012-2h14a2 2 0 012 2v8a2 2 0 01-2 2h-5l-5 5v-5z"
          />
        </svg>
        <h3>Messagerie</h3>
      </div>
      <div class="relative">
        <textarea v-model="message_content" id="" cols="10" rows="5"></textarea>
        <button
          class="
            px-14
            py-2
            absolute
            right-2
            top-40
            text-white
            bg-blue-800
            rounded-md
          "
        >
          Envoyer
        </button>
      </div>
    </div>
  </div>
</template>

<script>
import { mapActions } from "vuex";
export default {
  data() {
    return {
      message_content: "",
    };
  },
  computed: {
    payments() {
      return this.$store.state.payment.payments;
    },
    entree() {
      var msgTotal = this.payments.reduce(function (prev, cur) {
        return prev + cur.amount;
      }, 0);
      return msgTotal;
    },
  },
  mounted() {
    this.loadPay();
  },
  methods: {
    ...mapActions({ loadPay: "payment/loadPayment" }),
  },
};
</script>