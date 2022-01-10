<template>
  <div class="bg-gradient-to-r from-gray-900 via-indigo-900 to-blue-900 min-h-screen">
    <div class="max-w-6xl mx-auto py-12 px-4 sm:px-6 lg:py-20 lg:px-12">
      <h1 class="text-5xl font-medium tracking-wide text-white font-baloo">Find Your Course</h1>
      <h1 class="text-3xl font-medium tracking-wide text-white font-baloo">AWS, GCP et Azure : API, Dispo et scalabilité</h1>

      <div class="flex flex-col mt-6">
        <div class="-my-2 overflow-x-auto sm:-mx-6 lg:-mx-8">
          <div class="py-2 align-middle inline-block min-w-full sm:px-6 lg:px-8">
            <div class="shadow overflow-hidden border-b border-gray-200 sm:rounded-lg">
              <table class="min-w-full divide-y divide-gray-200">
                <thead class="bg-gray-50">
                  <tr>
                    <th scope="col" class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Code</th>
                    <th scope="col" class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Type</th>
                    <th scope="col" class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Message</th>
                    <th scope="col" class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Signification</th>
                  </tr>
                </thead>
                <tbody class="bg-white divide-y divide-gray-200">
                  <tr v-for="(code, index) in httpCodes" :key="index">
                    <td class="px-6 py-4 whitespace-nowrap">
                      <div class="flex items-center">
                        <div class="">
                          <div class="text-sm font-medium text-gray-900">{{ code.Code }}</div>
                        </div>
                      </div>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <div class="text-sm text-gray-900">{{ code.Type }}</div>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <div class="text-sm text-gray-500">{{ code.Message }}</div>
                    </td>
                    <td class="px-6 py-4">
                      <div class="text-sm text-gray-500">{{ code.Signification }}</div>
                    </td>
                  </tr>
                </tbody>
              </table>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  head() {
    return {
      title: 'Serverless APP | FYC'
    }
  },

  data() {
    return {
      httpCodes : []
    }
  },

  mounted () {
    this.$axios.$get('https://wygt10r8oe.execute-api.eu-west-2.amazonaws.com/default/handleGoogleSheetsAPI')
      .then(response => this.httpCodes = response).then(code => console.log(code))
  }
}
</script>
