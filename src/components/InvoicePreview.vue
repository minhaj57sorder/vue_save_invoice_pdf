<template>
  <div class="container mg-fw-5">
    <div class="row bottom-line">
      <div class="col text-start">
        <img class="template-logo" src="../assets/logo.png" alt="">
      </div>
      <div class="col text-end">
        <div class="mg-fw-7 mg-fs-13">
          {{invoiceDatas.business.name}}
        </div>
        <div class="mg-fs-08">
          {{invoiceDatas.business.address}}
        </div>
        <div class="mg-fs-08">
          {{invoiceDatas.business.phone}}
        </div>
        <div class="mg-fs-08">
          {{invoiceDatas.business.email}}
        </div>
        <div class="mg-fs-08">
          {{invoiceDatas.business.email_1}}
        </div>
        <div class="mg-fs-08">
          {{invoiceDatas.business.website}}
        </div>
      </div>
    </div>
    <div class="row align-content-center">
      <div class="col text-start mg-fs-08">
        <div class="mg-fs-09">{{ invoiceDatas.contact.label }}</div>
        <div class="mg-fs-12">{{ invoiceDatas.contact.name }}</div>
        <div class="">{{ invoiceDatas.contact.address }}</div>
        <div class="">{{ invoiceDatas.contact.phone }}</div>
        <div class="">{{ invoiceDatas.contact.email }}</div>
        <div class="">{{ invoiceDatas.contact.otherInfo }}</div>
      </div>
      <div class="col text-end">
        <div class="mg-fs-12">{{ invoiceDatas.invoice.label }} {{ invoiceDatas.invoice.num }}</div>
        <div class="">{{ invoiceDatas.invoice.invDate }}</div>
        <div class="">{{ invoiceDatas.invoice.invGenDate }}</div>
      </div>
    </div>
    <div class="row mg-fs-10 text-start">
      <div class="col-1">
        {{ invoiceDatas.invoice.header[0].title }}
      </div>
      <div class="col-2">
        {{ invoiceDatas.invoice.header[1].title }}
      </div>
      <div class="col-5">
        {{ invoiceDatas.invoice.header[2].title }}
      </div>
      <div class="col-1">
        {{ invoiceDatas.invoice.header[3].title }}
      </div>
      <div class="col-1">
        {{ invoiceDatas.invoice.header[4].title }}
      </div>
      <div class="col-1">
        {{ invoiceDatas.invoice.header[5].title }}
      </div>
      <div class="col-1">
        {{ invoiceDatas.invoice.header[6].title }}
      </div>
    </div>
    <div v-for="(tableItem, key) in invoiceDatas.invoice.table" :key="key" class="row top-line mg-fs-08 text-start">
      <div class="col-1">
        {{ tableItem[0] }}
      </div>
      <div class="col-2">
        {{ tableItem[1] }}
      </div>
      <div class="col-5">
        {{ tableItem[2] }}
      </div>
      <div class="col-1">
        {{ tableItem[3] }}
      </div>
      <div class="col-1">
        {{ tableItem[4] }}
      </div>
      <div class="col-1">
        {{ tableItem[5] }}
      </div>
      <div class="col-1">
        {{ tableItem[6] }}
      </div>
    </div>
    <div class="row mt-4 mg-fw-6">
      <div class="col"></div>
      <div class="col top-line pt-4">
        <div class="row mg-fs-12 text-end">
          <div class="col-3 text-start">
            <div>{{ invoiceDatas.invoice.additionalRows[0].col1 }}</div>
          </div>
          <div class="col-7">
            <div>{{ invoiceDatas.invoice.additionalRows[0].col2 }}</div>
            
          </div>
          <div class="col-2">
            <div>{{ invoiceDatas.invoice.additionalRows[0].col3 }}</div>

          </div>
        </div>
        <div class="row mg-fs-08 text-end">
          <div class="col-3 text-start">
            <div>{{ invoiceDatas.invoice.additionalRows[1].col1 }}</div>
          </div>
          <div class="col-7">
            <div>{{ invoiceDatas.invoice.additionalRows[1].col2 }}</div>
            
          </div>
          <div class="col-2">
            <div>{{ invoiceDatas.invoice.additionalRows[1].col3 }}</div>

          </div>
        </div>
        <div class="row mg-fs-08 text-end">
          <div class="col-3 text-start">
            <div>{{ invoiceDatas.invoice.additionalRows[2].col1 }}</div>
          </div>
          <div class="col-7">
            <div>{{ invoiceDatas.invoice.additionalRows[2].col2 }}</div>
            
          </div>
          <div class="col-2">
            <div>{{ invoiceDatas.invoice.additionalRows[2].col3 }}</div>

          </div>
        </div>
      </div>
    </div>
    <div class="row">
      <div class="col-6">
        <div class="mt-2 text-start">
          <div class="mg-fs-10 mg-fw-6">{{ invoiceDatas.invoice.invDescLabel }}</div>
          <div class="mg-fs-07">{{ invoiceDatas.invoice.invDesc }}</div>
        </div>

      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'InvoicePreview',
  props: {
    invoiceDatas:Object,
        },
  methods:{
    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>

</style>
