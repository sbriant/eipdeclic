##Eip Declic API Doc 

This README would normally document whatever steps are necessary to get your application up and running.

This Rest API is used to manage EipDeclic functions externally (Mobile app iphone, android ...)
-----------

* Eip Declic Api
* Version 1.0-SNAPSHOT
* [Eip Declic site](http://www.declic.co)

### Set up 

#### Configuration

* Base url : http://www.declic.co/rest
* HTTP Methods GET POST
* Response Request Doby : JSON

### Index

* NAME : index
* URI : index.php
* METHOD : GET
* RESPONSE BODY : 

```xml
{"message":"index"}
```

### Authentification

* NAME : checkCredentials (login)
* URI : checkCredentials.php
* METHOD : POST
* REQUEST BODY

```xml
{
  "credentials": 
    {
      "username": "xxx", 
      "password": "xxx"
    }
}
```

* Keep this json in App memory to reuse it with query that need authentification

* RESPONSE BODY

```xml
{
   "message": true
}
```

### Logout

* To logout just programmatically remove credential object from app memory

### Profils :

* Subscription
* Mandatory fields : nick_name password

```xml
{
  "users":
    {
      "nick_name":"yy",
      "password":"yy"
    }
}
```

* NAME : createProfil (subscription)
* URI : createProfil.php
* METHOD : POST
* REQUEST BODY : all fields
 
```xml
{
  "profils":
    {
      "age":"30",
      "department":"75",
      "job":"yy",
      "birth_place":"yy",
      "first_name":"yy",
      "iq_score":"80",
      "last_name":"yy",
      "profil_type":"WORKER",
      "student_level":"6"
    },
  "users":
    {
      "email":"yy",
      "nick_name":"yy",
      "password":"yy"
    }
}
```

* Errors : 
* if email already exists : return HTTP 412
* if nickName already exists : return HTTP 409
* else return HTTP 200

* NAME : getAllProfils
* URI : getAllProfils.php
* METHOD : POST
* REQUEST BODY :
 
```xml
}
  "credentials": 
    {
      "username": "admin", 
      "password": "admin"
    }
}
```

* RESPONSE BODY :
```xml
{
   "users":
   [
       {
           "id_users": "4",
           "nick_name": "admin"
       },
       {
           "id_users": "9",
           "nick_name": "ee"
       }
   ],
   "profils":
   [
       {
           "id_users": "4",
           "first_name": "admin",
           "last_name": "admin",
           "age": "30",
           "profil_type": "WORKER",
           "job": "admin",
           "student_level": "6",
           "iq_score": "80",
           "birth_place": "admin",
           "department": "75"
       },
       {
           "id_users": "9",
           "first_name": "ee",
           "last_name": "ee",
           "age": "0",
           "profil_type": "",
           "job": "",
           "student_level": "0",
           "iq_score": "0",
           "birth_place": "",
           "department": "0"
       }
   ]
}
```

* NAME : getProfil
* URI : getProfil.php
* METHOD : POST
* REQUEST BODY :
```xml
{
  "credentials": 
    {
      "username": "admin", 
      "password": "admin"
    }
}
```

* RESPONSE BODY :
```xml
{
   "users":
   [
       {
           "id_users": "4",
           "email": "admin@admin.com",
           "password": "admin",
           "role": "admin",
           "enabled": "1",
           "nick_name": "admin"
       }
   ],
   "profils":
   [
       {
           "id_users": "4",
           "first_name": "admin",
           "last_name": "admin",
           "age": "30",
           "profil_type": "WORKER",
           "job": "admin",
           "student_level": "6",
           "iq_score": "80",
           "birth_place": "admin",
           "department": "75"
       }
   ]
}
```

* NAME : editProfil
* URI : editProfil.php
* METHOD : POST
* REQUEST BODY :
 
```xml 
{
    "credentials": 
    {
      "username": "admin", 
      "password": "admin"
    }, 
   "profils":
       {
           "id_users": "4",
           "first_name": "admin",
           "last_name": "admin",
           "age": "30",
           "profil_type": "WORKER",
           "job": "admin",
           "student_level": "6",
           "iq_score": "80",
           "birth_place": "admin",
           "department": "75"
       }
}
```

* RESPONSE BODY
```xml
 
```

### Get Methods

* NAME : getOrderedDepartments
* URI : getOrderedDepartments.php

* NAME : getOrderedDepartmentsObject
* URI : getOrderedDepartmentsObject.php

* NAME : emailAlreadyExists
* URI : emailAlreadyExists.php?email=xxx

* NAME : nickNameAlreadyExists
* URI : nickNameAlreadyExists.php?nickName=xxx

### EducationTips
 
* NAME : addEducationTips
* URI : addEducationTips.php
* METHOD : POST
* REQUEST BODY

```xml
{
  "credentials": 
    {
      "username": "admin", 
      "password": "admin"
    }, 
  "educationTips": 
  {
   "id_education_tips": "1",
   "title": "dd",
   "descriptions": "dd",
   "categories": "dd",
   "picture": "dd",
   "link": "dd",
   "vote": "1",
   "public": "1",
   "id_users": "4"
   }
}
```

* NAME : getAllEducationsTips
* URI : getAllEducationsTips.php?group=xxx

* NAME : getAllEducationTipsByGroupCategoriesObject
* URI : getAllEducationTipsByGroupCategoriesObject.php?group=xxx

* NAME : getAllEducationTipsByUserId
* URI : getAllEducationTipsByUserId.php?idUsers=xxx

* NAME : getAllEducationTipsObject
* URI : getAllEducationTipsObject.php

* NAME : addTipsComment
* URI : addTipsComment.php?id=xxx
* id = educationTipsId

* REQUEST BODY

```xml
{
  "tipsComment" : "comment"
}
```

* NAME : addVoteEducationTips
* URI : addVoteEducationTips.php?idEducationTips=xxx&vote=xxx

* NAME : getAllEducationTipsByGroupCategories
* URI : getAllEducationTipsByGroupCategories.php

* METHOD : POST
* REQUEST BODY
 
```xml
{
  "credentials": 
    {
      "username": "xxx", 
      "password": "xxx"
    }
}
```

* RESPONSE BODY
 
```xml
[
   {
       "id_education_tips": "1",
       "title": "dd",
       "descriptions": "dd",
       "categories": "dd",
       "picture": "dd",
       "link": "dd",
       "vote": "2",
       "public": "1",
       "id_users": "4"
   },
   {
       "id_education_tips": "3",
       "title": "test",
       "descriptions": "test",
       "categories": "dd",
       "picture": "dd",
       "link": "dd",
       "vote": "2",
       "public": "2",
       "id_users": "4"
   }
]
```

* NAME : getFriendsEducationTips
* URI : getFriendsEducationTips.php
* METHOD : POST
* REQUEST BODY
 
```xml
{
  "credentials": 
    {
      "username": "admin", 
      "password": "admin"
    }
}
```

* RESPONSE BODY
 
```xml
[
   {
       "id_education_tips": "7",
       "title": "ee",
       "descriptions": "ee",
       "categories": "ee",
       "picture": "ee",
       "link": "ee",
       "vote": "2",
       "public": "3",
       "id_users": "9"
   }
]
```

* NAME : addVoteEducationTips
* URI : addVoteEducationTips.php?idEducationTips=6&vote=2
* METHOD : POST
* REQUEST BODY : 
* REQUEST BODY
 
```xml
{
  "credentials": 
    {
      "username": "admin", 
      "password": "admin"
    }
}
```

* RESPONSE BODY

```xml
{"message":"addVoteEducationTips"}
```

* NAME : editEducationTips
* URI : editEducationTips.php
* METHOD : POST
* REQUEST BODY
 
```xml
{
  "credentials": 
    {
      "username": "admin", 
      "password": "admin"
    }, 
  "educationTips": [
  {
   "id_education_tips": "1",
   "title": "dd",
   "descriptions": "dd",
   "categories": "dd",
   "picture": "dd",
   "link": "dd",
   "vote": "1",
   "public": "1",
   "id_users": "4"
   }
   ]
}
```

### Friends
 
* NAME : addFriend
* URI : addFriend.php?id=15
* METHOD : POST
* REQUEST BODY
 
```xml
}
  "credentials": 
    {
      "username": "admin", 
      "password": "admin"
    }
}
```

* NAME : deleteFriend
* URI : deleteFriend.php?id=15
* METHOD : POST
* REQUEST BODY 
 
```xml
}
  "credentials": 
    {
      "username": "admin", 
      "password": "admin"
    }
}
```

* NAME : getFriends
* URI : getFriends.php
* METHOD : POST
* RESPONSE BODY
 
```xml
[
   {
       "id_users": "9",
       "nick_name": "ee",
       "email": "ee@ee.com",
       "first_name": "ee",
       "last_name": "ee",
       "age": "0",
       "profil_type": "",
       "job": "",
       "student_level": "0",
       "iq_score": "0",
       "birth_place": "",
       "department": "0"
   }
]
```

* NAME : getFriendsByFirstNameAndLastName
* URI : getFriendsByFirstNameAndLastName.php?firstName=ee&lastName=ee
* METHOD : POST
* RESPONSE BODY

```xml
[
   {
       "id_users": "9",
       "nick_name": "ee",
       "email": "ee@ee.com",
       "first_name": "ee",
       "last_name": "ee",
       "age": "0",
       "profil_type": "",
       "job": "",
       "student_level": "0",
       "iq_score": "0",
       "birth_place": "",
       "department": "0"
   }
]
```

* NAME : isFriend
* URI : isFriend.php?idUsers=1
* METHOD : POST
* REQUEST BODY

```xml
}
  "credentials": 
    {
      "username": "admin", 
      "password": "admin"
    }
}
```

* RESPONSE BODY :

```xml
{
   "message": false
}
```

### News

* NAME : getMyNews
* URI : getMyNews.php
* METHOD : POST
* REQUEST BODY
 
```xml
}
  "credentials": 
    {
      "username": "xxx", 
      "password": "xxx"
    }
}
```

* RESPONSE BODY

```xml
[
   {
       "id_news": "1",
       "title": "ff",
       "descriptions": "ff",
       "date": "2014-03-31 16:19:37"
   }
]
```

* NAME : getPublicHomeNewsCorporate
* URI : getPublicHomeNewsCorporate.php

* NAME : getPublicHomeNews
* URI : getPublicHomeNews.php

* NAME : addNewsComment
* URI : addNewsComment.php?id=xxx
* id = newsId
* REQUEST BODY
 
```xml
{
  "newsComment": "comment"
}
```

* name : addVoteNews
* URI : addVoteNews.php?idNews=xxx&vote=xxx

* NAME : addNews
* URI : addNews.php
* METHOD : POST
* REQUEST BODY
 
```xml
{
    "credentials": {
        "username": "yy",
        "password": "yy"
    },
    "news": 
        {
            "id_news": "1",
            "title": "ffééé",
            "descriptions": "",
            "date": "2014-03-31 16:19:37",
            "id_users": null
        }
    
}
```

* RESPONSE BODY

```xml 
{"message":"addNews"}
```

* NAME : editNews
* URI : editMyNews.php
* METHOD : POST
* REQUEST BODY
 
```xml
{
    "credentials": {
        "username": "admin",
        "password": "admin"
    },
    "news": 
        {
            "id_news": "1",
            "title": "ffééé",
            "descriptions": "",
            "date": "2014-03-31 16:19:37",
            "id_users": null
        }
    
}
```

* RESPONSE BODY

```xml
{"message":"editNews"}
```

* NAME : getAllNews
* URI : getAllNews.php
* METHOD : POST
* REQUEST BODY


```xml
}
  "credentials": 
    {
      "username": "admin", 
      "password": "admin"
    }
}
```

* RESPONSE BODY

```xml
[
   {
       "id_news": "1",
       "title": "ff",
       "descriptions": "ff",
       "date": "2014-03-31 16:19:37"
   }
]
```

* NAME : getOrderedNewsObject
* URI : getOrderedNewsObject.php

* NAME : getOrderedNews
* URI : getOrderedNews.php
* METHOD : POST
* REQUEST BODY

```xml
}
  "credentials": 
    {
      "username": "admin", 
      "password": "admin"
    }
}
```

* RESPONSE BODY

```xml
[
   {
       "id_news": "1",
       "title": "ff",
       "descriptions": "ff",
       "date": "2014-03-31 16:19:37"
   }
]
```

* NAME : getLastNews
* URI : getLastNews.php
* METHOD : POST
* REQUEST BODY
 
```xml
}
  "credentials": 
    {
      "username": "admin", 
      "password": "admin"
    }
}
```

* RESPONSE BODY

```xml
[
   {
       "id_news": "1",
       "title": "ff",
       "descriptions": "ff",
       "date": "2014-03-31 16:19:37"
   }
]
```

* NAME : addVoteNews
* URI : addVoteNews.php?idNews=6&vote=2
* METHOD : POST
* REQUEST BODY
 
```xml
}
  "credentials": 
    {
      "username": "admin", 
      "password": "admin"
    }
}
```

* RESPONSE BODY
```xml
{"message":"addVoteNews"}
```

### Pratitioner
 
* NAME : getAllPratitioner
* URI : getAllPratitioner.php
* METHOD : POST

* NAME : getAllPratitionerObject
* URI : getAllPratitionerObject.php

* NAME : getAllPratitionerByDepartments
* URI : getAllPratitionerByDepartments.php?department=75

### Organisations

* NAME : getAllOrganisations
* URI : getAllOrganisations.php
* METHOD : POST
* REQUEST BODY

```xml
}
  "credentials": 
    {
      "username": "admin", 
      "password": "admin"
    }
}
```

* RESPONSE BODY

```xml
[
   {
       "id_organisations": "1",
       "title": "test",
       "descriptions": "",
       "department": "75"
   }
]
```

* NAME : getAllOrganisationsObject
* URI : getAllOrganisationsObject.php

* NAME : getAllOrganisationsByDepartments
* URI : getAllOrganisationsByDepartments.php?department=75
* METHOD : POST
* REQUEST BODY :

```xml
}
  "credentials": 
    {
      "username": "admin", 
      "password": "admin"
    }
}
```

* RESPONSE BODY

```xml
[
   {
       "id_organisations": "1",
       "title": "test",
       "descriptions": "",
       "department": "75"
   }
]
```

### Schools

* NAME : getAllSchools
* URI : getAllSchools.php
* METHOD : POST
* REQUEST BODY :

```xml
}
  "credentials": 
    {
      "username": "admin", 
      "password": "admin"
    }
}
```

* RESPONSE BODY

```xml
[
   {
       "id_schools": "1",
       "title": "test",
       "descriptions": "test",
       "department": "75"
   },
   {
       "id_schools": "2",
       "title": "ffDD",
       "descriptions": "",
       "department": "75"
   }
]
```

* NAME : getAllSchoolsObject
* URI : getAllSchoolsObject.php

* NAME : getAllSchoolsByDepartments
* URI : getAllSchoolsByDepartments.php?department=75
* METHOD : POST
* REQUEST BODY :
```xml
}
  "credentials": 
    {
      "username": "admin", 
      "password": "admin"
    }
}
```

* RESPONSE BODY
```xml
[
   {
       "id_schools": "1",
       "title": "test",
       "descriptions": "test",
       "department": "75"
   },
   {
       "id_schools": "2",
       "title": "ffDD",
       "descriptions": "",
       "department": "75"
   }
]
```