<template>
  <div>
    <div class="mt-4 sm:mt-0">
      <div class="md:grid md:grid-cols-1 md:gap-6 px-12">
        <div class="mt-2 md:mt-0 md:col-span-2">
          <div class="px-4 sm:px-0">
            <h3 class="font-medium leading-6 text-gray-900">
              Information General
            </h3>
          </div>
          <form action="#" method="POST">
            <div class="shadow overflow-hidden sm:rounded-md">
              <div class="px-12 py-5 bg-white">
                <div class="flex flex-col space-y-4">
                  <div class="flex space-x-4">
                    <div class="w-1/2">
                      <label
                        for="first-name"
                        class="block text-sm font-medium text-gray-700"
                        >Denomination</label
                      >
                      <input
                        type="text"
                        name="first-name"
                        id="first-name"
                        autocomplete="given-name"
                        v-model="company.name"
                        class="
                          mt-1
                          focus:ring-indigo-500
                          focus:border-indigo-500
                          block
                          w-full
                          shadow-sm
                          sm:text-sm
                          border-gray-300
                          rounded-md
                        "
                      />
                    </div>
                    <div class="w-1/4">
                      <label
                        for="email-address"
                        class="block text-sm font-medium text-gray-700"
                        >Rccm</label
                      >
                      <input
                        type="text"
                        name="rccm"
                        id="rccm"
                        v-model="company.rccm"
                        placeholder="R-C-C-M"
                        class="
                          mt-1
                          focus:ring-indigo-500
                          focus:border-indigo-500
                          block
                          w-full
                          shadow-sm
                          sm:text-sm
                          border-gray-300
                          rounded-md
                        "
                      />
                    </div>
                    <div class="w-1/4">
                      <label
                        for="email-address"
                        class="block text-sm font-medium text-gray-700"
                        >Id national</label
                      >
                      <input
                        type="text"
                        name="id_nat"
                        id="id_nat"
                        placeholder="Id-nat"
                        v-model="company.id_nat"
                        class="
                          mt-1
                          focus:ring-indigo-500
                          focus:border-indigo-500
                          block
                          w-full
                          shadow-sm
                          sm:text-sm
                          border-gray-300
                          rounded-md
                        "
                      />
                    </div>
                  </div>
                  <div class="flex items-center w-full space-x-4">
                    <div class="col-span-6">
                      <label
                        for="street-address"
                        class="block text-sm font-medium text-gray-700"
                        >Votre Ville</label
                      >
                      <input
                        type="text"
                        name="street-address"
                        id="street-address"
                        v-model="company.address.city"
                        autocomplete="street-address"
                        placeholder="L'adresse de l'entreprise"
                        class="
                          mt-1
                          focus:ring-indigo-500
                          focus:border-indigo-500
                          block
                          w-full
                          shadow-sm
                          sm:text-sm
                          border-gray-300
                          rounded-md
                        "
                      />
                    </div>
                    <div class="flex-1">
                      <label
                        for="street-address"
                        class="block text-sm font-medium text-gray-700"
                        >Votre adresse</label
                      >
                      <input
                        type="text"
                        name="street-address"
                        id="street-address"
                        v-model="company.address.local"
                        autocomplete="street-address"
                        placeholder="L'adresse de l'entreprise"
                        class="
                          mt-1
                          focus:ring-indigo-500
                          focus:border-indigo-500
                          block
                          w-full
                          shadow-sm
                          sm:text-sm
                          border-gray-300
                          rounded-md
                        "
                      />
                    </div>
                  </div>

                  <div class="flex w-full space-x-4">
                    <div class="w-1/2">
                      <label
                        for="city"
                        class="block text-sm font-medium text-gray-700"
                        >Phone</label
                      >
                      <input
                        type="text"
                        name="phone"
                        id="phone"
                        v-model="company.contacts.phone"
                        placeholder="Ex: +243 84 999 . . ."
                        class="
                          mt-1
                          focus:ring-indigo-500
                          focus:border-indigo-500
                          block
                          w-full
                          shadow-sm
                          sm:text-sm
                          border-gray-300
                          rounded-md
                        "
                      />
                    </div>

                    <div class="w-1/2">
                      <label
                        for="state"
                        class="block text-sm font-medium text-gray-700"
                        >Email</label
                      >
                      <input
                        type="text"
                        name="email"
                        id="email"
                        placeholder="exemple@gmail.com"
                        v-model="company.contacts.email"
                        class="
                          mt-1
                          focus:ring-indigo-500
                          focus:border-indigo-500
                          block
                          w-full
                          shadow-sm
                          sm:text-sm
                          border-gray-300
                          rounded-md
                        "
                      />
                    </div>
                  </div>

                  <div class="">
                    <label
                      for="about"
                      class="block text-sm font-medium text-gray-700"
                    >
                      description
                    </label>
                    <div class="mt-1">
                      <textarea
                        id="about"
                        v-model="company.description"
                        name="about"
                        rows="3"
                        class="
                          shadow-sm
                          focus:ring-indigo-500
                          focus:border-indigo-500
                          mt-1
                          block
                          w-full
                          sm:text-sm
                          border border-gray-300
                          rounded-md
                        "
                        placeholder="Detail ici ...."
                      ></textarea>
                    </div>
                    <p class="mt-2 text-sm text-gray-500">
                      Brief description pour l'entreprise.
                    </p>
                  </div>
                </div>
              </div>

              <div class="px-12 py-3 bg-gray-50 text-right space-x-4">
                <nuxt-link
                  to="/settings/general"
                  class="
                    inline-flex
                    justify-center
                    py-2
                    px-20
                    border border-transparent
                    shadow-sm
                    text-sm
                    font-medium
                    rounded-md
                    text-white
                    bg-orange-600
                    hover:bg-orange-700
                    focus:outline-none
                    focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500
                  "
                >
                  Annuler
                </nuxt-link>
                <button
                  @click.prevent="updateComp"
                  class="
                    inline-flex
                    justify-center
                    py-2
                    px-20
                    border border-transparent
                    shadow-sm
                    text-sm
                    font-medium
                    rounded-md
                    text-white
                    bg-indigo-600
                    hover:bg-indigo-700
                    focus:outline-none
                    focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500
                  "
                >
                  Enregistrer
                </button>
              </div>
            </div>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { mapActions } from "vuex";
import gql from "graphql-tag";
export default {
  async asyncData({ app }) {
    let client = app.apolloProvider.defaultClient;

    const res = await client
      .query({
        query: gql`
          {
            company {
              id
              name
              description
              contacts {
                email
                phone
              }
              rccm
              id_nat
              address {
                city
                local
              }
            }
          }
        `,
      })
      .then(({ data }) => {
        //console.log(data);
        return data && data.company;
      });

    console.log(res);

    return {
      company: res,
    };
  },
  // mounted(){
  //   this.getCompany();

  //   this.company=this.$store.state.company.company;
  //   console.log(this.company);
  // },
  methods: {
    ...mapActions({ updateCompany: "company/updateCompany" }),
    updateComp() {
      this.updateCompany({
        name: this.company.name,
        description: this.company.description,
        rccm: this.company.rccm,
        id_nat: this.company.id_nat,
        address: {
          city: this.company.address.city,
          local: this.company.address.local,
        },
        contacts: {
          email: this.company.contacts.email,
          phone: this.company.contacts.phone,
        },
      });
    },
  },
};
</script>