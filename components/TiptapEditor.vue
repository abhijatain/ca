<template>
    <div v-if="editor" class="container">
    
      <editor-content :editor="editor" />
    </div>
  </template>
  
  <script>
  import Table from '@tiptap/extension-table'
  import TableCell from '@tiptap/extension-table-cell'
  import TableHeader from '@tiptap/extension-table-header'
  import TableRow from '@tiptap/extension-table-row'
  import StarterKit from '@tiptap/starter-kit'
  import { Editor, EditorContent } from '@tiptap/vue-3'
  
  const CustomTableCell = TableCell.extend({
    addAttributes() {
      return {
        // extend the existing attributes …
        ...this.parent?.(),
  
        // and add a new one …
        backgroundColor: {
          default: null,
          parseHTML: element => element.getAttribute('data-background-color'),
          renderHTML: attributes => {
            return {
              'data-background-color': attributes.backgroundColor,
              style: `background-color: ${attributes.backgroundColor}`,
            }
          },
        },
      }
    },
  })
  
  export default {
    components: {
      EditorContent,
    },
  
    data() {
      return {
        editor: null,
    
      }
    },
  
    mounted() {
      this.editor = new Editor({
        extensions: [
          StarterKit,
          Table.configure({
            resizable: true,
          }),
          TableRow,
          TableHeader,
          // Default TableCell
          // TableCell,
          // Custom TableCell with backgroundColor attribute
          CustomTableCell,
        ],
        content: `
          <p>Question 1</p> <p>On 1st April, 2023, Green Limited started the construction of an Office Building (qualified asset). The land under the building is regarded as a separate asset and is not a part of qualifying asset.</p> <table> <tr> <th>Amount of Loan</th> <th>Rate of Interest per annum</th> </tr> <tr> <td> 20,00,000</td> <td>15%</td> </tr> <tr> <td> 30,00,000</td> <td>8%</td> </tr> </table> <p>The company's specific loan of  14 lakhs was raised from a Bank at an interest rate of 12% per annum. An interest income of  15,000 was earned on this loan while it was held in anticipation of payments.</p> <p>The construction of building started on 1st April, 2023 and was completed on 31st January, 2024 when it was ready for its intended use. Up to the date of completion of the building, the following payments were made to the contractor:</p> <table> <tr> <th>Payment date</th> <th>Amount in </th> </tr> <tr> <td>1st April, 2023</td> <td>4,00,000</td> </tr> <tr> <td>1st August, 2023</td> <td>10,00,000</td> </tr> <tr> <td>1st December, 2023</td> <td>25,00,000</td> </tr> <tr> <td>31st January, 2024</td> <td>5,00,000</td> </tr> </table> <p>The life of building is estimated to be 20 years and depreciation is calculated on straight line method.</p> <p>Well Wear Limited is a Textile Manufacturing Company and engaged in the production of Polyester (P) and Nylon (N). While manufacturing the main products, a by-product Fiber (F) is also produced.</p> <table> <tr> <th>Purchase of Raw Material</th> <th>Amount in </th> </tr> <tr> <td>for manufacturing 30,000 units</td> <td> 3,50,000</td> </tr> </table> <p>Output:</p> <ul> <li>Polyester (P) - 12,500 Units</li> <li>Nylon (N) - 10,000 Units</li> <li>Fiber (F) - 3,200 Units</li> </ul> <p>Closing Inventory:</p> <table> <tr> <th>Material</th> <th>Units</th> </tr> <tr> <td>Polyester (P)</td> <td>1,600 Units</td> </tr> <tr> <td>Nylon (N)</td> <td>400 Units</td> </tr> </table> <p>Average market price of Polyester and Nylon is  100 and  60 per unit respectively, by-product Fiber is sold@ 40 per unit. There is a profit of  8,000 on sale of by-product after incurring separate processing expenses of  10,000 and packing charges of  9,000.  5,000 was realized from sale of scrap.</p>
         
        `,
      })
    },
  
    beforeUnmount() {
      this.editor.destroy()
    },
  }
  </script>
  
  <style lang="scss">
  /* Basic editor styles */
  .tiptap {
    :first-child {
      margin-top: 0;
    }
  
    /* List styles */
    ul,
    ol {
      padding: 0 1rem;
      margin: 1.25rem 1rem 1.25rem 0.4rem;
  
      li p {
        margin-top: 0.25em;
        margin-bottom: 0.25em;
      }
    }
  
    /* Heading styles */
    h1,
    h2,
    h3,
    h4,
    h5,
    h6 {
      line-height: 1.1;
      margin-top: 2.5rem;
      text-wrap: pretty;
    }
  
    h1,
    h2 {
      margin-top: 3.5rem;
      margin-bottom: 1.5rem;
    }
  
    h1 {
      font-size: 1.4rem;
    }
  
    h2 {
      font-size: 1.2rem;
    }
  
    h3 {
      font-size: 1.1rem;
    }
  
    h4,
    h5,
    h6 {
      font-size: 1rem;
    }
  
    /* Code and preformatted text styles */
    code {
      background-color: var(--purple-light);
      border-radius: 0.4rem;
      color: var(--black);
      font-size: 0.85rem;
      padding: 0.25em 0.3em;
    }
  
    pre {
      background: var(--black);
      border-radius: 0.5rem;
      color: var(--white);
      font-family: 'JetBrainsMono', monospace;
      margin: 1.5rem 0;
      padding: 0.75rem 1rem;
  
      code {
        background: none;
        color: inherit;
        font-size: 0.8rem;
        padding: 0;
      }
    }
  
    blockquote {
      border-left: 3px solid var(--gray-3);
      margin: 1.5rem 0;
      padding-left: 1rem;
    }
  
    hr {
      border: none;
      border-top: 1px solid var(--gray-2);
      margin: 2rem 0;
    }
  
    /* Table-specific styling */
    table {
      border-collapse: collapse;
      margin: 0;
      overflow: hidden;
      table-layout: fixed;
      width: 100%;
      border: 1px solid var(--gray-3); /* added border to table */
  
      td,
      th {
        border: 1px solid var(--gray-3);
        box-sizing: border-box;
        min-width: 1em;
        padding: 6px 8px;
        position: relative;
        vertical-align: top;
  
        > * {
          margin-bottom: 0;
        }
      }
  
      th {
        background-color: var(--gray-1);
        font-weight: bold;
        text-align: left;
      }
  
      .selectedCell:after {
        background: var(--gray-2);
        content: "";
        left: 0; right: 0; top: 0; bottom: 0;
        pointer-events: none;
        position: absolute;
        z-index: 2;
      }
  
      .column-resize-handle {
        background-color: var(--purple);
        bottom: -2px;
        pointer-events: none;
        position: absolute;
        right: -2px;
        top: 0;
        width: 4px;
      }
    }
  
    .tableWrapper {
      margin: 1.5rem 0;
      overflow-x: auto;
      border: 1px solid var(--gray-3); /* added border to table wrapper */
    }
  
    &.resize-cursor {
      cursor: ew-resize;
      cursor: col-resize;
    }
  }
  </style>
  
  