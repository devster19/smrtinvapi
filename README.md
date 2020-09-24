FORMAT: 1A
HOST: https://polls.apiblueprint.org/

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
                    "branch": { 
                        "branchId": "b783343", 
                        "nameEN": "Central RAMA IX", 
                        "nameTH": "เซนทรัล พระราม 9"
                    },
                    "shop":  { 
                        "shopId": "s018ee3", 
                        "nameEN": "Beleive Store", 
                        "nameTH": "บีลีฟ สโตร์"
                    },
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
                                "description": "",
                                "checked": true
                            },
                            { 
                                "id": "ae76865-002",
                                "name": "ค่าไฟ",
                                "value": "31,345.00", 
                                "description": "",
                                "checked": true
                            },
                            { 
                                "id": "ae76865-003",
                                "name": "ค่าน้ำ",
                                "value": "3,463.25", 
                                "description": "",
                                "checked": true
                            }
                        ]
                    },
                    "createDate": "2019-07-25T08:45:00",
                    "endDate": "2020-07-25T08:45:00",
                    "checked": true
                },
                {
                    "invoiceId": "dd76865",
                    "paymentStatus":false,
                    "branch": { 
                        "branchId":"bd22676", 
                        "nameEN": "Central RAMA IX", 
                        "nameTH": "เซนทรัล พระราม 9"
                    },
                    "shop":  { 
                        "shopId":"sd22676", 
                        "nameEN": "Beleive ฺBakery",
                        "nameTH": "บีลีฟ เบเกอรี่"
                    },
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
                    "createDate": "2020-01-25T08:45:00",
                    "endDate": "2021-01-25T08:45:00",
                    "checked": false
                },
                {
                    "invoiceId": "dd76865",
                    "paymentStatus":false,
                    "branch": { 
                        "branchId": "d345999", 
                        "nameEN": "Central  Bagna", 
                        "nameTH": "เซนทรัล บางนา"
                    },
                    "shop": { 
                        "shopId": "s783343", 
                        "nameEN": "Beleive Electronics", 
                        "nameTH": "บีลีฟ อิเล็กทรอนิกส์"
                    },
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
                    "createDate": "2019-07-25T08:45:00",
                    "endDate": "2020-07-25T08:45:00",
                    "checked": false
                }
            ]
        }
        
       
        

### Filter and Order Invoices list by BranchId  [POST]
* แสดงรายการบิลที่จะจ่ายโดยมีการกรองข้อมูล
* { filter: null } แสดงรายการทั้งหมดถ้าไม่มีการส่งข้อมูลมา
* { filter: { branches: [], sort: []} } กรองข้อมูลที่จะแสดงจากสาขา หรือ ร้าน หรือทั้งสองเงื่อนไขรวมกัน

+ Request (application/json)

    + Headers 
    
            Authorization: eyJjb250cmFjdElkIjoiMTIzNDU2Nzg5MCJ9
    
            
+ Request (application/json)

        {
        
            "filter": {
                "branches": ["b783343"],
                "sort": ["duedate"]
            }
                
        }

+ Response 200 (application/json)

        {
            "totalAmount": "796,000.75",
            "data": [ 
                {
                    "invoiceId": "ae76865",
                    "paymentStatus":false,
                    "branch": { 
                        "branchId": "b783343", 
                        "nameEN": "Central RAMA IX",
                        "nameTH": "เซนทรัล พระราม 9"
                    },
                    "shop":  { 
                        "shopId": "s018ee3", 
                        "nameEN": "Beleive Store", 
                        "nameTH": "บีลีฟ สโตร์" 
                    },
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
                                "description": "",
                                "checked": true
                            },
                            { 
                                "id": "ae76865-002",
                                "name": "ค่าไฟ",
                                "value": "31,345.00", 
                                "description": "",
                                "checked": true
                            },
                            { 
                                "id": "ae76865-003",
                                "name": "ค่าน้ำ",
                                "value": "3,463.25", 
                                "description": "",
                                "checked": true
                            }
                        ]
                    },
                    "createDate": "2019-04-22T08:45:00",
                    "endDate": "2020-04-22T08:45:00",
                    "checked": false
                },
                {
                    "invoiceId": "dd76865",
                    "paymentStatus":false,
                    "branch": { 
                        "branchId": "b783343", 
                        "nameEN": "Central RAMA IX", 
                        "nameTH": "เซนทรัล พระราม 9"
                    },
                    "shop":  { 
                        "shopId": "s783343", 
                        "nameEN": "Beleive Electronics", 
                        "nameTH": "บีลีฟ อิเล็กทรอนิกส์"
                    },
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
                                "description": "",
                                "checked": true
                            },
                            { 
                                "id": "dd76865-002",
                                "name": "ค่าไฟ",
                                "value": "31,345.00", 
                                "description": "",
                                "checked": true
                            },
                            { 
                                "id": "dd76865-003",
                                "name": "ค่าน้ำ",
                                "value": "3,463.25", 
                                "description": "",
                                "checked": true
                            }
                        ]
                    },
                    "createDate": "2019-07-25T08:45:00",
                    "endDate": "2020-07-25T08:45:00",
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
            "data":[
            {
                    "invoiceId": "ae76865",
                    "paymentStatus":false,
                    "branch": { 
                        "branchId": "b783343", 
                        "nameEN": "Central RAMA IX", 
                        "nameTH": "เซนทรัล พระราม 9"
                    },
                    "shop":  { 
                        "shopId": "s018ee3", 
                        "nameEN": "Beleive Store", 
                        "nameTH": "บีลีฟ สโตร์"
                    },
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
                                "description": "",
                                "checked": true
                            },
                            { 
                                "id": "ae76865-002",
                                "name": "ค่าไฟ",
                                "value": "31,345.00", 
                                "description": "",
                                "checked": true
                            },
                            { 
                                "id": "ae76865-003",
                                "name": "ค่าน้ำ",
                                "value": "3,463.25", 
                                "description": "",
                                "checked": true
                            }
                        ]
                    },
                    "createDate": "2019-07-25T08:45:00",
                    "endDate": "2020-07-25T08:45:00",
                    "checked": true
                }
            ],
            "paymentChannel":"kbank",
            "requestBillType":"include",
            "requestEmail":"test@mail.com"
        }
        
+ Response 201 (application/json)

    + Body

            {
                "transactionId": "d7e992f3",
                "transactionType": "PURCHASE",
                "billPayment": {
                    "paymentAmount": "234,763.25",
                    "accountTo": "123456789012345",
                    "ref1": "ae76865"
                },
                "data": [ 
                {
                    "invoiceId": "ae76865",
                    "branch": { 
                        "branchId": "b783343", 
                        "nameEN": "Central RAMA IX", 
                        "nameTH": "เซนทรัล พระราม 9"
                    },
                    "shop":  { 
                        "shopId": "s018ee3", 
                        "nameEN": "Beleive Store", 
                        "nameTH": "บีลีฟ สโตร์"
                    },
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
                                "description": "",
                                "checked": true
                            },
                            { 
                                "id": "ae76865-002",
                                "name": "ค่าไฟ",
                                "value": "31,345.00", 
                                "description": "",
                                "checked": true
                            },
                            { 
                                "id": "ae76865-003",
                                "name": "ค่าน้ำ",
                                "value": "3,463.25", 
                                "description": "",
                                "checked": true
                            }
                        ]
                    },
                    "createDate": "2019-07-25T08:45:00",
                    "endDate": "2020-07-25T08:45:00",
                    "checked": false
                },
                
            ],
            "paymentDate": "2020-07-25T08:45:00",
            "paymentChannel":"kbank",
            "requestBillType":"include",
            "requestEmail":"test@mail.com"
            }

### Update Payment Item per Invoice  [Patch]
+ Request (application/json)

    + Headers 
    
            Authorization: eyJjb250cmFjdElkIjoiMTIzNDU2Nzg5MCJ9
    + Request (application/json)

        {
            "data":[
                {
                    "invoiceId": "ae76865",
                    "paymentDetails":{
                        "paymentItems":
                        [
                            {
                                "id": "ae76865-001",
                                "name": "ค่าเช่า",
                                "value": "200,000.00",
                                "description": "",
                                "checked": false
                            },
                            { 
                                "id": "ae76865-002",
                                "name": "ค่าไฟ",
                                "value": "31,345.00", 
                                "description": "",
                                "checked": true
                            },
                            { 
                                "id": "ae76865-003",
                                "name": "ค่าน้ำ",
                                "value": "3,463.25", 
                                "description": "",
                                "checked": true
                            }
                        ]
                    }
                }
            ]
        }
        
+ Response 201 (application/json)

    + Body

            {
                "transactionId": "d7e992f3",
                "transactionType": "PURCHASE",
                "billPayment": {
                    "paymentAmount": "234,763.25",
                    "accountTo": "123456789012345",
                    "ref1": "ae76865"
                },
                "data": [ 
                {
                    "invoiceId": "ae76865",
                    "branch": { 
                        "branchId": "b783343", 
                        "nameEN": "Central RAMA IX", 
                        "nameTH": "เซนทรัล พระราม 9"
                    },
                    "shop":  { 
                        "shopId": "s018ee3", 
                        "nameEN": "Beleive Store", 
                        "nameTH": "บีลีฟ สโตร์"
                    },
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
                                "description": "",
                                "checked": false
                            },
                            { 
                                "id": "ae76865-002",
                                "name": "ค่าไฟ",
                                "value": "31,345.00", 
                                "description": "",
                                "checked": true
                            },
                            { 
                                "id": "ae76865-003",
                                "name": "ค่าน้ำ",
                                "value": "3,463.25", 
                                "description": "",
                                "checked": true
                            }
                        ]
                    },
                    "createDate": "2019-07-25T08:45:00",
                    "endDate": "2020-07-25T08:45:00",
                    "checked": true
                },
                
            ]
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
                        "branch": { 
                            "branchId": "b783343", 
                            "nameEN": "Central RAMA IX", 
                            "nameTH": "เซนทรัล พระราม 9"
                        },
                        "shop":  { 
                            "shopId": "s018ee3", 
                            "nameEN": "Beleive Store", 
                            "nameTH": "บีลีฟ สโตร์" 
                        },
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
                        "createDate": "2019-07-25T08:45:00",
                        "endDate": "2020-07-25T08:45:00",
                        "checked": false
                    },
                    {
                        "invoiceId": "dd76865",
                        "paymentStatus":"paid",
                        "branch": { 
                            "branchId": "b783343", 
                            "nameEN": "Central RAMA IX", 
                            "nameTH": "เซนทรัล พระราม 9"
                        },
                        "shop":  { 
                            "shopId": "s783343", 
                            "nameEN": "Beleive Electronics", 
                            "nameTH": "บีลีฟ อิเล็กทรอนิกส์"
                        },
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
                        "createDate": "2019-07-25T08:45:00",
                        "endDate": "2020-07-25T08:45:00",
                        "checked": false
                    }
                ],
                
                "paymentDate": "2020-07-25T08:45:00"
                
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
                        "branch": { 
                            "branchId": "b783343", 
                            "nameEN": "Central RAMA IX", 
                            "nameTH": "เซนทรัล พระราม 9"
                        },
                        "shop":  { 
                            "shopId": "s018ee3", 
                            "nameEN": "Beleive Store", 
                            "nameTH": "บีลีฟ สโตร์"
                        },
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
                        "createDate": "2019-07-25T08:45:00",
                        "endDate": "2020-07-25T08:45:00",
                        "checked": false
                    }
                    ],
                    "paymentDate": "2020-07-25T08:45:00"
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
            "paymentDate": "2020-07-25T08:45:00",
            "downloadPath": "/assets/purchase-a7e992f3.pdf"
        }


            
