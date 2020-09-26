# Exams-Edubook

Requirements :
1. MongoDB
2. Flask
3. MongoEngine


API's:
1. Create exam (subcategory is optional)
==>
POST Request - http://localhost:5000/exam
Body:
{
    "name":"IIT-JEE"
}

OR

{
    "name":"IIT-JEE1",
    "subcategory" : "Engineering"
}

2. Get the list of all exams
==>
GET REquest - http://localhost:5000/exam

3. Add sub-categories, subjects and topics under an exam only one record at a time.
==>
PUT Request - http://localhost:5000/exam
Body:

{
       "name": "XAT",
       "subcategory": {
           "CSE1" : {
                   "Databases" : ["rdms", "nosql"]
                   },
            "CSE2" : {
                   "Databases" : ["rdms", "nosql"],
                   "Databases2" : ["rdms", "nosql"]
                   }
       }
}

4. Get the entire hierarchy of an exam, its sub-categories their subjects and topics.
==>
GET Request - http://localhost:5000/exam/GATE5

Body:
{
    "_id": {
        "$oid": "5f6f43c831243b7a51f0843b"
    },
    "name": "GATE5",
    "subcategory": [
        {
            "name": "Computer Science3",
            "subjects": []
        },
        {
            "name": "Electrical3",
            "subjects": []
        },
        {
            "name": "CSE",
            "subjects": [
                {
                    "name": "Databases",
                    "topics": [
                        "rdms",
                        "nosql"
                    ]
                }
            ]
        },
        {
            "name": "CSE",
            "subjects": [
                {
                    "name": "Databases",
                    "topics": [
                        "rdms",
                        "nosql"
                    ]
                }
            ]
        },
        {
            "name": "CSE",
            "subjects": [
                {
                    "name": "Databases",
                    "topics": [
                        "rdms",
                        "nosql"
                    ]
                }
            ]
        },
        {
            "name": "CSE4",
            "subjects": [
                {
                    "name": "Databases2",
                    "topics": [
                        "rdms",
                        "nosql"
                    ]
                }
            ]
        }
    ],
    "subjects": []
}
