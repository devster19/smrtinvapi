FORMAT: 1A
HOST: https://polls.apiblueprint.org/

# Invoice

Simple API allowing users to view and manage theirs invoice request.

## Invoice by Branch Collection [/invoice/{branchId}]

### List All Payments [GET]

+ Request (application/json)

    + Headers 
    
            Authorization: eyJjb250cmFjdElkIjoiMTIzNDU2Nzg5MCJ9

+ Response 200 (application/json)

        
        {
            "branchId": "000008783",
            "brandName":{"en": "Central RAMA IX", "th": "เซนทรัล พระราม 9"},
            "totalAmout": "561,728.05"
            "data": [
                {
                    "shopId": "a0ee8414",
                    "shopName":"Believe Store Premium",
                    "status": "overdue",
                    "amount":"234,763.25",
                    "discount": "20,000.00",
                    "vatValue": "2,763.00",
                    "taxValue": "1,190.00",
                    "createDate": "2019-07-25T08:45:00Z",
                    "endDate": "2020-07-25T08:45:00Z",
                    "checked": true
                },
                {
                    "shopId": "b0ee8414",
                    "shopName":"Believe Store Gold",
                    "status": "overdue",
                    "amount":"336,768.50",
                    "discount": "",
                    "vatValue": "",
                    "taxValue": "",
                    "createDate": "2019-07-25T08:45:00Z",
                    "endDate": "2020-07-25T08:45:00Z",
                    "checked": true
                },
                {
                    "shopId": "c0ee8414",
                    "shopName":"Believe Store",
                    "status": "due",
                    "amount":"336,768.50",
                    "discount": "",
                    "vatValue": "",
                    "taxValue": "",
                    "createDate": "2019-07-25T08:45:00Z",
                    "endDate": "2020-07-25T08:45:00Z",
                    "checked": false
                },
                
            ]
        }
        

### Create Selected Payments [POST]

+ Request (application/json)

    + Headers 
    
            Authorization: eyJjb250cmFjdElkIjoiMTIzNDU2Nzg5MCJ9
            
+ Request (application/json)

        {
        
            "data": [
                {
                    "shopId": "a0ee8414",
                    "shopName":"Believe Store Premium",
                    "status": "overdue",
                    "amount":"234,763.25",
                    "discount": "20,000.00",
                    "vatValue": "2,763.00",
                    "taxValue": "1,190.00",
                    "createDate": "2019-07-25T08:45:00Z",
                    "endDate": "2020-07-25T08:45:00Z",
                    "checked": true
                },
                {
                    "shopId": "b0ee8414",
                    "shopName":"Believe Store Gold",
                    "status": "overdue",
                    "amount":"336,768.50",
                    "discount": "",
                    "vatValue": "",
                    "taxValue": "",
                    "createDate": "2019-07-25T08:45:00Z",
                    "endDate": "2020-07-25T08:45:00Z",
                    "checked": true
                },
                "note": "ชำระค่าบิลร้าน Premium และ Gold",
                "paymentMethod": "Internet Banking"
            ]
                
        }

+ Response 200 (application/json)

        {
            "result": "successful",
            "id": "inv209873",
            "totalAmount":"582,8789.00"
            "taxId": "01289387983",
            "taxValue": "18,763.00",
            "data": [
                {
                    "shopId": "a0ee8414",
                    "shopName":"Believe Store Premium",
                    "status": "overdue",
                    "amount":"234,763.25",
                    "discount": "20,000.00",
                    "vatValue": "2,763.00",
                    "taxValue": "1,190.00",
                    "createDate": "2019-07-25T08:45:00Z",
                    "endDate": "2020-07-25T08:45:00Z",
                },
                {
                    "shopId": "b0ee8414",
                    "shopName":"Believe Store Gold",
                    "status": "overdue",
                    "amount":"336,768.50",
                    "discount": "",
                    "vatValue": "",
                    "taxValue": "",
                    "createDate": "2019-07-25T08:45:00Z",
                    "endDate": "2020-07-25T08:45:00Z",
                },
            ],
            "note": "ชำระค่าบิลร้าน Premium และ Gold",
            "notificationStatus": true,
            "createDate": "2019-08-30T08:45:00Z"
        }

## Invoice by ShopId Collection  [/maintenance/{branchId}/{shopId}]

### Create a New Payment by ShopId [POST]

+ Request (application/json)

    + Headers 
    
            Authorization: eyJjb250cmFjdElkIjoiMTIzNDU2Nzg5MCJ9
            
+ Request (application/json)

        {
            "data": [
                {
                    "invoiceId": "bb2562987",
                    "items":[
                        {
                            "name": "ค่าเช่า",
                            "value": "200,000.00",
                        },
                        { 
                            "name": "ค่าไฟ",
                            "value": "31,345.00", 
                        },
                        { 
                            "name": "ค่าน้ำ",
                            "value": "3,463.25", 
                        }
                    ]
                },
                {
                    "invoiceId": "cd2763876",
                    "items":[
                        { 
                            "name": "ค่าแอร์",
                            "value": "500.00"
                        }
                    ]
                }
            ]
                
        }
        
+ Response 201 (application/json)

    + Body

            {
                "result": "Created",
                "id": "c0746f59",
                "shopName":"Believe Store",
                "status": "due",
                "totalAmount":"336,768.50",
                "data": [
                    {
                        "invoiceId": "bb2562987",
                        "items":[
                            {
                                "name": "ค่าเช่า",
                                "value": "200,000.00",
                                "checked": true
                            },
                            { 
                                "name": "ค่าไฟ",
                                "value": "31,345.00", 
                                "checked": true
                            },
                            { 
                                "name": "ค่าน้ำ",
                                "value": "3,463.25", 
                                "checked": true
                            }
                        ]
                    },
                    {
                        "invoiceId": "cd2763876",
                        "items":[
                            { 
                                "name": "ค่าแอร์",
                                "value": "500.00",
                                "checked": true 
                            }
                        ]
                    }
                ],
                "notificationStatus": false,
                "createDate": "2020-07-25T08:45:00Z",
                "endDate": "2020-08-25T08:45:00Z"
            }


### Get Invoice by ShopId [GET]

+ Request (application/json)

    + Headers 
     
            Authorization: eyJjb250cmFjdElkIjoiMTIzNDU2Nzg5MCJ9

+ Response 200 (application/json)

        
        {
            "id": "c0746f59",
            "shopName":"Believe Store",
            "status": "due",
            "totalAmount":"336,768.50",
            "data": [
                {
                    "invoiceId": "bb2562987",
                    "items":[
                        {
                            "name": "ค่าเช่า",
                            "value": "200,000.00",
                            "checked": true
                        },
                        { 
                            "name": "ค่าไฟ",
                            "value": "31,345.00", 
                            "checked": true
                        },
                        { 
                            "name": "ค่าน้ำ",
                            "value": "3,463.25", 
                            "checked": true
                        }
                    ]
                },
                {
                    "invoiceId": "cd2763876",
                    "items":[
                        { 
                            "name": "ค่าแอร์",
                            "value": "500.00",
                            "checked": true 
                        }
                    ]
                }
            ],
            "createDate": "2020-07-25T08:45:00Z",
            "endDate": "2020-08-25T08:45:00Z"
        }

### Update Invoice by ShopId [PUT]

+ Request (application/json)

    + Headers 
    
            Authorization: eyJjb250cmFjdElkIjoiMTIzNDU2Nzg5MCJ9
            
+ Request (application/json)

        {
            "data": [
                {
                    "invoiceId": "bb2562987",
                    "items":[
                        {
                            "name": "ค่าเช่า",
                            "value": "200,000.00",
                            "checked": true
                        },
                        { 
                            "name": "ค่าไฟ",
                            "value": "31,345.00", 
                            "checked": true
                        },
                        { 
                            "name": "ค่าน้ำ",
                            "value": "3,463.25", 
                            "checked": true
                        }
                    ]
                }
            ]
        }

+ Response 201 (application/json)

    + Body

            {
                "result": "Updated",
                "id": "c0746f59",
                "shopName":"Believe Store",
                "status": "due",
                "totalAmount":"336,768.50",
                "data": [
                    {
                        "invoiceId": "bb2562987",
                        "items":[
                            {
                                "name": "ค่าเช่า",
                                "value": "200,000.00",
                                "checked": true
                            },
                            { 
                                "name": "ค่าไฟ",
                                "value": "31,345.00", 
                                "checked": true
                            },
                            { 
                                "name": "ค่าน้ำ",
                                "value": "3,463.25", 
                                "checked": true
                            }
                        ]
                    }
                ],
                "notificationStatus": false,
                "createDate": "2020-07-25T08:45:00Z",
                "endDate": "2020-08-25T08:45:00Z"
            }


            
