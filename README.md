

# Invoice
ตัวอย่าง API Response สำหรับใช้แสดงข้อมูลการชำระเงิน

## Invoice Collection [/invoice/]

### List All Invoice(s) [GET]
* แสดงรายการที่จะต้องจ่ายทั้งหมดโดยเรียงลำดับจากรอบบิลที่ใกล้จะถึงรอบจ่ายมากที่สุด
+ Request (application/json)

    + Headers 
    
            Authorization: eyJjb250cmFjdElkIjoiMTIzNDU2Nzg5MCJ9

+ Response 200 (application/json)

        {
            "totalAmount": "796,000.75",
            "data": [ 
                {
                    "invoiceId": "ae76865",
                    "paymentStatus":false,
                    "branch": { "branchId": "b783343", "nameEN": "Central RAMA IX", "nameTH": "เซนทรัล พระราม 9" },
                    "shop":  { "shopId": "s018ee3", "nameEN": "Beleive Store", "nameTH": "บีลีฟ สโตร์" },
                    "description": "",
                    "status": "overdue",
                    "paymentDetail":{
                        "total": "234,763.25",
                        "discout": "20,000.00",
                        "vatValue": "2,763.00",
                        "taxValue": "1,190.00",
                        "paymentItems":[
                            {
                                "id": "ae76865-001",
                                "name": "ค่าเช่า",
                                "value": "200,000.00",
                                "description": ""
                            },
                            { 
                                "id": "ae76865-002",
                                "name": "ค่าไฟ",
                                "value": "31,345.00", 
                                "description": ""
                            },
                            { 
                                "id": "ae76865-003",
                                "name": "ค่าน้ำ",
                                "value": "3,463.25", 
                                "description": ""
                            }
                        ]
                    },
                    "createDate": "2019-07-25T08:45:00Z",
                    "endDate": "2020-07-25T08:45:00Z",
                    "checked": false
                },
                {
                    "invoiceId": "dd76865",
                    "paymentStatus":false,
                    "branch": { "branchId": "b783343", "nameEN": "Central RAMA IX", "nameTH": "เซนทรัล พระราม 9" },
                    "shop":  { "shopId": "s783343", "nameEN": "Beleive Electronics", "nameTH": "บีลีฟ อิเล็กทรอนิกส์" },
                    "description": "",
                    "status": "overdue",
                    "paymentDetails":{
                        "total": "234,763.25",
                        "discout": "20,000.00",
                        "vatValue": "2,763.00",
                        "taxValue": "1,190.00",
                        "paymentItems":[
                            {
                                "id": "dd76865-001",
                                "name": "ค่าเช่า",
                                "value": "200,000.00",
                                "description": ""
                            },
                            { 
                                "id": "dd76865-002",
                                "name": "ค่าไฟ",
                                "value": "31,345.00", 
                                "description": ""
                            },
                            { 
                                "id": "dd76865-003",
                                "name": "ค่าน้ำ",
                                "value": "3,463.25", 
                                "description": ""
                            }
                        ]
                    },
                    "createDate": "2019-07-25T08:45:00Z",
                    "endDate": "2020-07-25T08:45:00Z",
                    "checked": false
                },
                {
                    "invoiceId": "dd76865",
                    "paymentStatus":false,
                    "branch": { "branchId":"bd22676", "nameEN": "Central RAMA IX", "nameTH": "เซนทรัล พระราม 9" },
                    "shop":  { "shopId":"sd22676", "nameEN": "Beleive ฺBakery", "nameTH": "บีลีฟ เบเกอรี่" },
                    "description": "",
                    "status": "overdue",
                    "paymentDetails":{
                        "total": "234,763.25",
                        "discout": "20,000.00",
                        "vatValue": "2,763.00",
                        "taxValue": "1,190.00",
                        "paymentItems":[
                            {
                                "id": "dd76865-001",
                                "name": "ค่าเช่า",
                                "value": "200,000.00",
                                "description": ""
                            },
                            { 
                                "id": "dd76865-002",
                                "name": "ค่าไฟ",
                                "value": "31,345.00", 
                                "description": ""
                            },
                            { 
                                "id": "dd76865-003",
                                "name": "ค่าน้ำ",
                                "value": "3,463.25", 
                                "description": ""
                            }
                        ]
                    },
                    "createDate": "2020-01-25T08:45:00Z",
                    "endDate": "2021-01-25T08:45:00Z",
                    "checked": false
                }
            ]
        }
        
       
        

### List Invoice(s) by BranchId, ShopId or by BranchId + ShopId  [POST]
* แสดงรายการบิลที่จะจ่ายโดยมีการกรองข้อมูล
* { "data": [] } แสดงรายการทั้งหมดถ้าไม่มีการส่งข้อมูลมา
* { "data": [{ "branchId": "",  "shopId": ""}] } กรองข้อมูลที่จะแสดงจากสาขา หรือ ร้าน หรือทั้งสองเงื่อนไขรวมกัน

+ Request (application/json)

    + Headers 
    
            Authorization: eyJjb250cmFjdElkIjoiMTIzNDU2Nzg5MCJ9
    
            
+ Request (application/json)

        {
        
            "data": [
                {
                    "branchId":"b783343",
                    "shopId":"",
                    
                }
            ]
                
        }

+ Response 200 (application/json)

        {
            "totalAmount": "796,000.75",
            "data": [ 
                {
                    "invoiceId": "ae76865",
                    "paymentStatus":false,
                    "branch": { "branchId": "b783343", "nameEN": "Central RAMA IX", "nameTH": "เซนทรัล พระราม 9" },
                    "shop":  { "shopId": "s018ee3", "nameEN": "Beleive Store", "nameTH": "บีลีฟ สโตร์" },
                    "description": "",
                    "status": "overdue",
                    "paymentDetails":{
                        "total": "234,763.25",
                        "discout": "20,000.00",
                        "vatValue": "2,763.00",
                        "taxValue": "1,190.00",
                        "paymentItems":[
                            {
                                "id": "ae76865-001",
                                "name": "ค่าเช่า",
                                "value": "200,000.00",
                                "description": ""
                            },
                            { 
                                "id": "ae76865-002",
                                "name": "ค่าไฟ",
                                "value": "31,345.00", 
                                "description": ""
                            },
                            { 
                                "id": "ae76865-003",
                                "name": "ค่าน้ำ",
                                "value": "3,463.25", 
                                "description": ""
                            }
                        ]
                    },
                    "createDate": "2019-07-25T08:45:00Z",
                    "endDate": "2020-07-25T08:45:00Z",
                    "checked": false
                },
                {
                    "invoiceId": "dd76865",
                    "paymentStatus":false,
                    "branch": { "branchId": "b783343", "nameEN": "Central RAMA IX", "nameTH": "เซนทรัล พระราม 9" },
                    "shop":  { "shopId": "s783343", "nameEN": "Beleive Electronics", "nameTH": "บีลีฟ อิเล็กทรอนิกส์" },
                    "description": "",
                    "status": "overdue",
                    "paymentDetails":{
                        "total": "234,763.25",
                        "discout": "20,000.00",
                        "vatValue": "2,763.00",
                        "taxValue": "1,190.00",
                        "paymentItems":[
                            {
                                "id": "dd76865-001",
                                "name": "ค่าเช่า",
                                "value": "200,000.00",
                                "description": ""
                            },
                            { 
                                "id": "dd76865-002",
                                "name": "ค่าไฟ",
                                "value": "31,345.00", 
                                "description": ""
                            },
                            { 
                                "id": "dd76865-003",
                                "name": "ค่าน้ำ",
                                "value": "3,463.25", 
                                "description": ""
                            }
                        ]
                    },
                    "createDate": "2019-07-25T08:45:00Z",
                    "endDate": "2020-07-25T08:45:00Z",
                    "checked": false
                }
               
            ]
        }
        
## Make a Payment [/invoice/payment/]

### Create a Single or Multiple Invoice(s) for Payment  [POST]
* ส่วนนี้เป็นการ คาดเดา Header ที่จะใช้ทำการส่ง อาจจะต้องคุยกับทางธนาคารก่อนว่าทำการส่งข้อมูลยังไง แต่จะมีการ ร่าง response เบื้องต้นไว้เพื่อซัพพอร์ตการแสดงผลของ UI
+ Request (application/json)

    + Headers 
    
            Authorization: eyJjb250cmFjdElkIjoiMTIzNDU2Nzg5MCJ9
            
+ Request (application/json)

        {
            "requestPaymentId": " d7e992f3-c9f1-4071-8a4a-6c5839c8d317",
            "refInvoiceIds":["ae76865","dd76865"],
            "channel":"kbank"
        }
        
+ Response 201 (application/json)

    + Body

            {
                "transactionId": "d7e992f3",
                "transactionType": "PURCHASE",
                "billPayment": {
                    "paymentAmount": "796,000.75",
                    "accountTo": "123456789012345",
                    "ref1": "ae76865",
                    "ref2": "dd76865"
                },
                "data": [ 
                {
                    "invoiceId": "ae76865",
                    "paymentStatus":false,
                    "branch": { "branchId": "b783343", "nameEN": "Central RAMA IX", "nameTH": "เซนทรัล พระราม 9" },
                    "shop":  { "shopId": "s018ee3", "nameEN": "Beleive Store", "nameTH": "บีลีฟ สโตร์" },
                    "description": "",
                    "status": "overdue",
                    "paymentDetails":{
                        "total": "234,763.25",
                        "discout": "20,000.00",
                        "vatValue": "2,763.00",
                        "taxValue": "1,190.00",
                        "paymentItems":[
                            {
                                "id": "ae76865-001",
                                "name": "ค่าเช่า",
                                "value": "200,000.00",
                                "description": ""
                            },
                            { 
                                "id": "ae76865-002",
                                "name": "ค่าไฟ",
                                "value": "31,345.00", 
                                "description": ""
                            },
                            { 
                                "id": "ae76865-003",
                                "name": "ค่าน้ำ",
                                "value": "3,463.25", 
                                "description": ""
                            }
                        ]
                    },
                    "createDate": "2019-07-25T08:45:00Z",
                    "endDate": "2020-07-25T08:45:00Z",
                    "checked": false
                },
                {
                    "invoiceId": "dd76865",
                    "paymentStatus":"paid",
                    "branch": { "branchId": "b783343", "nameEN": "Central RAMA IX", "nameTH": "เซนทรัล พระราม 9" },
                    "shop":  { "shopId": "s783343", "nameEN": "Beleive Electronics", "nameTH": "บีลีฟ อิเล็กทรอนิกส์" },
                    "description": "",
                    "status": "overdue",
                    "paymentDetails":{
                        "total": "234,763.25",
                        "discout": "20,000.00",
                        "vatValue": "2,763.00",
                        "taxValue": "1,190.00",
                        "paymentItems":[
                            {
                                "id": "dd76865-001",
                                "name": "ค่าเช่า",
                                "value": "200,000.00",
                                "description": ""
                            },
                            { 
                                "id": "dd76865-002",
                                "name": "ค่าไฟ",
                                "value": "31,345.00", 
                                "description": ""
                            },
                            { 
                                "id": "dd76865-003",
                                "name": "ค่าน้ำ",
                                "value": "3,463.25", 
                                "description": ""
                            }
                        ]
                    },
                    "createDate": "2019-07-25T08:45:00Z",
                    "endDate": "2020-07-25T08:45:00Z",
                    "checked": false
                }
            ],
            "paymentDate": "2020-07-25T08:45:00Z",
            }

### List All Invoice History [GET]
* แสดงประวัติการชำระใบแจ้งหนี้
+ Request (application/json)

    + Headers 
     
            Authorization: eyJjb250cmFjdElkIjoiMTIzNDU2Nzg5MCJ9

+ Response 200 (application/json)

        
        {
            "data" :[
                {
                    "transactionId": "d7e992f3",
                    "transactionType": "PURCHASE",
                    "billPayment": {
                        "paymentAmount": "796,000.75",
                        "accountTo": "123456789012345",
                        "ref1": "ae76865",
                        "ref2": "dd76865"
                    },
                    "data": [ 
                    {
                        "invoiceId": "ae76865",
                        "paymentStatus":false,
                        "branch": { "branchId": "b783343", "nameEN": "Central RAMA IX", "nameTH": "เซนทรัล พระราม 9" },
                        "shop":  { "shopId": "s018ee3", "nameEN": "Beleive Store", "nameTH": "บีลีฟ สโตร์" },
                        "description": "",
                        "status": "overdue",
                        "paymentDetails":{
                            "total": "234,763.25",
                            "discout": "20,000.00",
                            "vatValue": "2,763.00",
                            "taxValue": "1,190.00",
                            "paymentItems":[
                                {
                                    "id": "ae76865-001",
                                    "name": "ค่าเช่า",
                                    "value": "200,000.00",
                                    "description": ""
                                },
                                { 
                                    "id": "ae76865-002",
                                    "name": "ค่าไฟ",
                                    "value": "31,345.00", 
                                    "description": ""
                                },
                                { 
                                    "id": "ae76865-003",
                                    "name": "ค่าน้ำ",
                                    "value": "3,463.25", 
                                    "description": ""
                                }
                            ]
                        },
                        "createDate": "2019-07-25T08:45:00Z",
                        "endDate": "2020-07-25T08:45:00Z",
                        "checked": false
                    },
                    {
                        "invoiceId": "dd76865",
                        "paymentStatus":"paid",
                        "branch": { "branchId": "b783343", "nameEN": "Central RAMA IX", "nameTH": "เซนทรัล พระราม 9" },
                        "shop":  { "shopId": "s783343", "nameEN": "Beleive Electronics", "nameTH": "บีลีฟ อิเล็กทรอนิกส์" },
                        "description": "",
                        "status": "overdue",
                        "paymentDetails":{
                            "total": "234,763.25",
                            "discout": "20,000.00",
                            "vatValue": "2,763.00",
                            "taxValue": "1,190.00",
                            "paymentItems":[
                                {
                                    "id": "dd76865-001",
                                    "name": "ค่าเช่า",
                                    "value": "200,000.00",
                                    "description": ""
                                },
                                { 
                                    "id": "dd76865-002",
                                    "name": "ค่าไฟ",
                                    "value": "31,345.00", 
                                    "description": ""
                                },
                                { 
                                    "id": "dd76865-003",
                                    "name": "ค่าน้ำ",
                                    "value": "3,463.25", 
                                    "description": ""
                                }
                            ]
                        },
                        "createDate": "2019-07-25T08:45:00Z",
                        "endDate": "2020-07-25T08:45:00Z",
                        "checked": false
                    }
                ],
                
                "paymentDate": "2020-07-25T08:45:00Z"
                
                },
                {
                    "transactionId": "a7e992f3",
                    "transactionType": "PURCHASE",
                    "billPayment": {
                        "paymentAmount": "796,000.75",
                        "accountTo": "123456789012345",
                        "ref1": "ae76865",
                        "ref2": "dd76865"
                    },
                    "data": [ 
                    {
                        "invoiceId": "bb3212a2",
                        "paymentStatus":false,
                        "branch": { "branchId": "b783343", "nameEN": "Central RAMA IX", "nameTH": "เซนทรัล พระราม 9" },
                        "shop":  { "shopId": "s018ee3", "nameEN": "Beleive Store", "nameTH": "บีลีฟ สโตร์" },
                        "description": "",
                        "status": "overdue",
                        "paymentDetails":{
                            "total": "234,763.25",
                            "discout": "20,000.00",
                            "vatValue": "2,763.00",
                            "taxValue": "1,190.00",
                            "paymentItems":[
                                {
                                    "id": "ae76865-001",
                                    "name": "ค่าเช่า",
                                    "value": "200,000.00",
                                    "description": ""
                                },
                                { 
                                    "id": "ae76865-002",
                                    "name": "ค่าไฟ",
                                    "value": "31,345.00", 
                                    "description": ""
                                },
                                { 
                                    "id": "ae76865-003",
                                    "name": "ค่าน้ำ",
                                    "value": "3,463.25", 
                                    "description": ""
                                }
                            ]
                        },
                        "createDate": "2019-07-25T08:45:00Z",
                        "endDate": "2020-07-25T08:45:00Z",
                        "checked": false
                    }
                    ],
                    "paymentDate": "2020-07-25T08:45:00Z"
                }
            ]
        }
        

## Download Invoice  [/invoice/payment/{transactionId}]

### Download Invoice Document After Made a Purchase  [GET]
* พาธสำหรับทำการดาวน์โหลดไฟล์ รายการจ่ายใบชำระแจ้งหนี้

+ Request (application/json)

    + Headers 
     
            Authorization: eyJjb250cmFjdElkIjoiMTIzNDU2Nzg5MCJ9

+ Response 200 (application/json)

        
        {
            "transactionId": "a7e992f3",
            "paymentDate": "2020-07-25T08:45:00Z",
            "downloadPath": "/assets/purchase-a7e992f3.pdf"
        }


            
