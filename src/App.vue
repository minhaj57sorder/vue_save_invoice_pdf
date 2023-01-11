<template>
  <div ref="invoiceDiv">
    <InvoicePreview :invoiceDatas="invoiceDatas" />
  </div>
  <div class="mt-3 container">
    <button @click="download">Download Invoice</button>
    <button class="ms-3" @click="printInv">Print Invoice</button>
  </div>
</template>

<script>
import InvoicePreview from "./components/InvoicePreview.vue";
// import jsPDF from "jspdf";
import jsPDFInvoiceTemplate from "jspdf-invoice-template";
export default {
  name: "App",
  components: {
    InvoicePreview,
  },
  data() {
    return {
      invoiceDatas: {
        outputType: jsPDFInvoiceTemplate.datauristring,
        returnJsPDFDocObject: true,
        fileName: "Invoice 2021",
        orientationLandscape: false,
        compress: true,
        logo: {
          src: "./logo.png",
          type: "PNG", //optional, when src= data:uri (nodejs case)
          width: 53.33, //aspect ratio = width/height
          height: 26.66,
          margin: {
            top: 0, //negative or positive num, from the current position
            left: 0, //negative or positive num, from the current position
          },
        },
        stamp: {
          inAllPages: true, //by default = false, just in the last page
          src: "https://raw.githubusercontent.com/edisonneza/jspdf-invoice-template/demo/images/qr_code.jpg",
          type: "JPG", //optional, when src= data:uri (nodejs case)
          width: 20, //aspect ratio = width/height
          height: 20,
          margin: {
            top: 0, //negative or positive num, from the current position
            left: 0, //negative or positive num, from the current position
          },
        },
        business: {
          name: "Freelancing",
          address: "Sajjankanda,Rajbari",
          phone: "(+880) 12345678",
          email: "minhaj@example.com",
          email_1: "minhaj1@example.com",
          website: "www.minhajsorder.com",
        },
        contact: {
          label: "Invoice issued for:",
          name: "Mahadi",
          address: "Public health, Rajbari",
          phone: "(+880) 12345678",
          email: "mh@mahadihasan.com",
          otherInfo: "www.mahadihasan.com",
        },
        invoice: {
          label: "Invoice #: ",
          num: 1,
          invDate: "Payment Date: 09/01/2023 18:12",
          invGenDate: "Invoice Date: 11/01/2023 10:17",
          headerBorder: false,
          tableBodyBorder: false,
          header: [
            {
              title: "#",
              style: {
                width: 10,
              },
            },
            {
              title: "Title",
              style: {
                width: 30,
              },
            },
            {
              title: "Description",
              style: {
                width: 80,
              },
            },
            { title: "Price" },
            { title: "Quantity" },
            { title: "Unit" },
            { title: "Total" },
          ],
          table: Array.from(Array(10), (item, index) => [
            index + 1,
            "There are many variations ",
            "Lorem Ipsum is simply dummy text dummy text ",
            200.5,
            4.5,
            "m2",
            400.5,
          ]),
          additionalRows: [
            {
              col1: "Total:",
              col2: "145,250.50",
              col3: "ALL",
              style: {
                fontSize: 14, //optional, default 12
              },
            },
            {
              col1: "VAT:",
              col2: "20",
              col3: "%",
              style: {
                fontSize: 10, //optional, default 12
              },
            },
            {
              col1: "SubTotal:",
              col2: "116,199.90",
              col3: "ALL",
              style: {
                fontSize: 10, //optional, default 12
              },
            },
          ],
          invDescLabel: "Invoice Note",
          invDesc:
            "There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injected humour, or randomised words which don't look even slightly believable. If you are going to use a passage of Lorem Ipsum, you need to be sure there isn't anything embarrassing hidden in the middle of text. All the Lorem Ipsum generators on the Internet tend to repeat predefined chunks as necessary.",
        },
        footer: {
          text: "The invoice is created on a computer and is valid without the signature and stamp.",
        },
        pageEnable: true,
        pageLabel: "Page ",
      },
    };
  },
  methods: {
    download() {
      jsPDFInvoiceTemplate(this.invoiceDatas);
    },
    printInv() {
      let printable = window.open(
        "",
        "PRINT",
        "height=842,width=595"
      );
      let styles = document.getElementsByTagName('style')

      printable.document.write("</head><body >");
      printable.document.write(this.$refs.invoiceDiv.innerHTML);
      for(let i =0, l=styles.length; i < l; i++){
        printable.document.write(`<style> ${styles[i].innerHTML} </style>`);
      }
      printable.document.write("</body></html>");

      printable.document.close(); // necessary for IE >= 10
      printable.focus(); // necessary for IE >= 10*/

      printable.print();

      return true;
    },
  },
};
</script>
<style>
@import './assets/style.css';
</style>
