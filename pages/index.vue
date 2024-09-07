<template>
     <SideBar />
     <div class="flex flex-row justify-between p-4 ms-14 border-b">
                <Breadcrumb>
                    <BreadcrumbList>
                    <BreadcrumbItem>
                        <BreadcrumbLink href="/">
                        Home
                        </BreadcrumbLink>
                    </BreadcrumbItem>
                    <BreadcrumbSeparator>
                        /
                    </BreadcrumbSeparator>
                    <BreadcrumbItem>
                        <BreadcrumbLink href="/components">
                        Finals
                        </BreadcrumbLink>
                    </BreadcrumbItem>
                    <BreadcrumbSeparator>
                        /
                    </BreadcrumbSeparator>
                    <BreadcrumbItem>
                        <BreadcrumbLink href="/components">
                        AFM
                        </BreadcrumbLink>
                    </BreadcrumbItem>
                    
                    <BreadcrumbSeparator>
                        /
                    </BreadcrumbSeparator>
                    <BreadcrumbItem>
                        <BreadcrumbLink href="/components">
                        Questions
                        </BreadcrumbLink>
                    </BreadcrumbItem>
                    <BreadcrumbSeparator>
                        /
                    </BreadcrumbSeparator>
                    <BreadcrumbItem>
                        <BreadcrumbPage>Chapter 1</BreadcrumbPage>
                    </BreadcrumbItem>
                    </BreadcrumbList>
                </Breadcrumb>
                <span>Timer : 01:30:06</span>
            </div>
    <div class=" flex flex-row py-2  ms-14">
        
        <div class="w-[70%] border-r  flex flex-col">
            
          
            <div class="p-4">
                <Tabs default-value="account" >
                    <TabsList>
                    <TabsTrigger value="account">
                        Question
                    </TabsTrigger>
                    <TabsTrigger value="password">
                        Solution
                    </TabsTrigger>
                    </TabsList>
                    <TabsContent value="account">
                    
                        <ScrollArea class="h-[750px]  rounded-md border p-4">
    <client-only>
      <tiptap-editor />
    </client-only></ScrollArea>

                    
                    </TabsContent>
                    <TabsContent value="password">
                        <ScrollArea class="h-[750px]  rounded-md border p-4">
                            <img src="assets/3.png"/>
                            <img src="assets/4.png"/>
                            <img src="assets/5.png"/>
                            <img src="assets/6.png"/>

                        </ScrollArea>
                       
                    </TabsContent>
                </Tabs>
                
                
            </div>
            <div class="flex flex-row gap-2 p-2 m-2">
                <Button variant="outline">Mark as Answered</Button>
                <Button variant="outline">Mark for Review</Button>
                <Button variant="outline">Add a Note</Button>
                <Button variant="outline">Discussion</Button>
                

            </div>
        </div>
        <div class="w-[30%] py-2 flex flex-col gap-4">
            <Card class="border-0 border-b">
                <CardHeader>
                <CardTitle>Progress</CardTitle>
                <CardDescription>All the Unanswered and wrong answers are stored for future reference</CardDescription>
                </CardHeader>
                <CardContent>
                <div class="flex gap-4 flex-col">
                    <div class="flex gap-4">
                        <Button class="" >10</Button>
                        <span>Answered</span>
                    </div>
                    <div class="flex gap-4">
                        <Button variant="outline">18</Button> 
                        <span>Not Answered</span>
                    </div>
                    <div class="flex gap-4">
                        <Button variant="destructive">15</Button>
                         <span>Marked for Review</span>
                    </div>
                    
                </div>
                </CardContent>
            </Card>   
            <Card  class="border-0 ">
                <CardHeader>
                <CardTitle>Questions</CardTitle>
                <CardDescription>Select the question number to answer.</CardDescription>
                </CardHeader>
                <CardContent>
                    <ScrollArea class="h-[500px]  rounded-md border p-4">
                        <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-1">
                            <Button v-for="n in 20" :key="n" variant="" class="m-2">{{ n }}</Button>
                            <Button v-for="n in 10" :key="n" variant="outline" class="m-2">{{ n + 20 }}</Button>
                            <Button v-for="n in 10" :key="n" variant="destructive" class="m-2">{{ n + 30 }}</Button>
                        </div>
                    </ScrollArea>
                </CardContent>
            
            </Card>   
        </div>
    </div>
    
</template>

<script >

const solution = `
<table> <tr> <th>Particulars</th> <th>Debit</th> <th>Credit</th> </tr> <tr> <td>Building account</td> <td>₹ 45,70,000</td> <td></td> </tr> <tr> <td>Bank account</td> <td></td> <td>₹ 44,00,000</td> </tr> <tr> <td>Interest payable (borrowing cost)</td> <td></td> <td>₹ 1,70,000</td> </tr> </table> <p>(Being expenditure incurred on construction of building and borrowing cost thereon capitalized)</p> <h2>Depreciation on Building</h2> <p>Cost of building: ₹ 45,70,000</p> <p>Life of building: 20 years</p> <p>Depreciation: (45,70,000 / 20) x 2/12 = ₹ 38,083.33</p> <p>Carrying Value of Building on 31st March 2024:</p> <table> <tr> <th>Particulars</th> <th>Value</th> </tr> <tr> <td>Cost of building</td> <td>₹ 45,70,000</td> </tr> <tr> <td>Accumulated Depreciation</td> <td>₹ 38,083.33</td> </tr> <tr> <td>Carrying Value</td> <td>₹ 45,31,917</td> </tr> </table> <h2>Calculation of Weighted Average Accumulated Expenses</h2> <table> <tr> <th>Amount of Loan</th> <th>Rate of Interest</th> <th Amount of Interest</th> </tr> <tr> <td>₹ 20,00,000</td> <td>15%</td> <td>₹ 3,00,000</td> </tr> <tr> <td>₹ 30,00,000</td> <td>8%</td> <td>₹ 2,40,000</td> </tr> <tr> <td>₹ 50,00,000</td> <td>5.40%</td> <td>₹ 2,70,000</td> </tr> </table> <h2>Working Notes</h2> <p>Calculation of Capitalization Rate on Borrowings other than Specific Borrowings</p> <table> <tr> <th>Particulars</th> <th>Value</th> </tr> <tr> <td>Total expenses to be capitalized for building</td> <td>₹ 45,70,000</td> </tr> </table> <p>As per AS 2 ‘Valuation of Inventories’, most by-products as well as scrap or waste materials by their nature, are immaterial. They are often measured at net realizable value and this value is deducted from the cost of the main product.</p> <h2>Determination of Value of Closing Inventory of Polyester and Nylon</h2> <table> <tr> <th>Particulars</th> <th>Value</th> </tr> <tr> <td>Polyester</td> <td>₹ 49,824</td> </tr> <tr> <td>Nylon</td> <td>₹ 7,472</td> </tr> </table> <h2>Calculation of Net Realizable Value of By-product, Fiber</h2> <table> <tr> <th>Particulars</th> <th>Value</th> </tr> <tr> <td>Selling price of by-product Fiber</td> <td>₹ 1,28,000</td> </tr> <tr> <td>Separate processing charges of by-product Fiber</td> <td>₹ 10,000</td> </tr> <tr> <td>Packing charges</td> <td>₹ 9,000</td> </tr> <tr> <td>Net realizable value of by-product Fiber</td> <td>₹ 1,09,000</td> </tr> </table> <h2>Calculation of Cost of Conversion for Allocation between Joint Products Polyester and Nylon</h2> <table> <tr> <th>Particulars</th> <th>Value</th> </tr> <tr> <td>Raw material</td> <td>₹ 3,50,000</td> </tr> <tr> <td>Wages</td> <td>₹ 1,60,000</td> </tr> <tr> <td>Fixed overhead</td> <td>₹ 1,20,000</td> </tr> <tr> <td>Variable overhead</td> <td>₹ 60,000</td> </tr> <tr> <td>Less: NRV of by-product Fiber</td> <td>₹ 1,09,000</td> </tr> </table> <h2>Determination of “Basis for Allocation” and Allocation of Joint Cost to Polyester and Nylon</h2> <table> <tr> <th>Particulars</th> <th>Value</th> </tr> <tr> <td>Polyester</td> <td>12,500 units</td> </tr> <tr> <td>Nylon</td> <td>10,000 units</td> </tr> <tr> <td>Sales price per unit (a)</td> <td>₹ 100</td> </tr> <tr> <td>Sales value (a x b)</td> <td>₹ 12,50,000</td> </tr> <tr> <td>Sales value (10,000 units x 60)</td> <td>₹ 6,00,000</td> </tr> </table> <p>Joint cost of ₹ 5,76,000 allocated in the ratio of 12,50,000 : 6,00,000 = ₹ 3,89,189 : ₹ 1,86,811</p> <p>Cost per unit:</p> <table> <tr> <th>Particulars</th> <th>Value</th> </tr> <tr> <td>Polyester</td> <td>₹ 31.14</td> </tr> <tr> <td>Nylon</td> <td>₹ 18.68</td> </tr> </table> </div>

`
  import TiptapEditor from '~/components/TiptapEditor.vue'
  export default {
    components: {
      TiptapEditor,
    },
  }
</script>