# week-24-create-strapi-database
MIT xPro Week 23 - Video 24.10

You’ll set up a [Strapi](https://strapi.io/)database with Postman, which you’ll use to complete the GraphQL exercise.

In order to follow along with the code in this video, it is required that your node version installed is between 10.16.0 and 14.x.x. You can check this by running the ```node -v``` command in your terminal/shell. If you need to switch between different versions of node frequently for compatibility issues between projects, it is recommended to use a tool like NVM (node version manager) for [Linux/Mac](https://github.com/nvm-sh/nvm) or Windows Links to an external site..

Note: When running the `npx create-strapi-app…’ command shown in the video at approximately 0:33, be sure to specify strapi version 3 on the command by typing: 

```npx create-strapi-app@3 myStrapi --quickstart```

The later instructions will not match if you use a different version of strapi.

If you get an error saying 'node-pre-gyp' is not recognized as an internal or external command, navigate inside of your newly created `myStrapi` folder and run the following commands:

```yarn install```

```yarn strapi build```

```yarn strapi develop```

If your Strapi UI looks different than the videos when you are setting permissions, follow these instructions:

Go to Settings > USERS & PERMISSIONS PLUGIN: Roles > Public > Permissions: Application > Select all
Go to COLLECTION TYPES > Accounts > Make sure "State" is "Published"

Now you can hit ```localhost:1337/accounts``` from Postman.

Strapi builds a database and specify the structure of the database and an application program interface(API).

Postman tests the API.

1. Install Strapi version 3 in your directory. It is named ```learning-strapi```. It will create a server and use a default database to store the data that we create. After the server is created, then the browser opens.

```npx create-strapi-app@3 learning-strapi --quickstart```

2. Create a super-user in the browser.

3. Create collection type "account" with three text fields. "name","email","password". Then add a few new accounts.

4. Hit strappi with Postman

GET ```localhost:1337/accounts``` Send

This is forbidden. Probably because of Strapi authorizations.

5. Roles & Permissions

Edit Public
- select all 'account' permisions.

6. Hit Strapi, now it works.

7. GET ```localhost:1337/accounts``` Send

- Header Key = ```content-type```, Value = ```application.json```

- body is ```raw```, ```json```

```
{
        "name": "Postman",
        "email": "postman@strapi.com",
        "password": "007"
}
```

8. In Postman, you see the code snipets for the "POST" command. You see what the curl code or fetch code would be used to POST data to strapi.

```
curl --location --request GET 'localhost:1337/accounts' \
--header 'Content-Type: application/json' \
--data-raw '{
        "name": "Postman",
        "email": "postman@strapi.com",
        "password": "007"
}'
```





