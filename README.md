Collab-a-Block API

###Our Schema
db.createCollection("Residents",{
   validator:{
      $jsonSchema{
          bsonType:"object",
          required:["streetNumber", "address", "owner"],
          properties: {
               streetNumber: {
                     bsonType: "number",
                     description: "must be a neutral or positive value",
               },
               address: {
                     bsonType: "object",
                     required: ["postcode", "street"],
                     properties: {
                         postcode: {
                             bsonType: "string",
                             description: "must be a string of 6 characters",
                         },
                         street: {
                             bsonType: "string",
                             description: "must be a string",
                         }
               }
               owner: {
                     bsonType: "object",
                     required: ["name", "age", "residentNumber"],
                     properties: {
                         name: {
                             bsonType: "string",
                             description: "must be a string",
                         },
                         age: {
                             bsonType: "number",
                             description: "must be a neutral or positive value",,
                         }
                         residentnumber: {
                             bsonType: "number",
                             description: "must be a neutral or positive value",
                         }
                }                         
            }
          }
       }
   })
