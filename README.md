# Bachelor's Thesis: "*DayDay, appointment scheduling for clinics*"

### Author :bust_in_silhouette:: Inés Nieto Sánchez :octocat: [@ins426](https://github.com/ins426)
### Tutor :bust_in_silhouette:: Rocío Celeste Romero Zaliz
___
## Introduction ✏️
After seven years of Carmen Verdejo clinic's opening, their personnel has decided that it is time to progress and to put faith in platforms that can speed up those slow administrative processes, such as clinic appointments. It is common for many companies, and specially the small ones, to be reluctant to change, they don't trust other solutions for their tasks apart from the tranditional ones. In this case, Carmen Verdejo clinic has tested some tools for their appointment scheduling, general as well as specific ones. On the one hand, the general ones were too complicated to adapt for such as simple user flow. On the other hand, specific software products offered too many funcionalities, they were expensive and the most important factor, it was really hard to learn how to use them. That's how this project was born, it aims to create an intuitive platform for scheduling appointments. In this platform, with a role system for permission management, users will be able to create, edit and remove appointments, so current traditional scheduling appointments methodology is sped up for those tasks.
___
## Code 🖥️
This project's code is divided into frontend and backend part that conforms the chosen stack which is **MEAN stack** (MongoDB, Express.js, Angular and Node.js). Each part, frontend and backend, has its own repository:
1. [DayDay frontend](https://github.com/ins426/TFG-frontend), it represents the 'A' initial.
2. [DayDay backend](https://github.com/ins426/TFG-backend), it represents the 'M','E','N' initials.
___
## Tools 🧰
- [Docker-compose](https://docs.docker.com/compose) and [Docker](https://www.docker.com/) were used to facilitate deployment. In order to launch this platform, there are some requirements. Let's see backend configuration:
  1. Firstly, execute ```git clone git@github.com:ins426/TFG.git``` on your terminal and a new directory called ```TFG``` is created.
  2. **Database configuration**: In  [MongoDB Atlas](https://www.mongodb.com/es/atlas) create a database named ```dd_db``` and two collections: ```appointments``` and ```users```. After that, create a ```.env``` file in TFG/TFG-backend and add ```MONGODB_ATLAS_USER=<your_user>``` and ```MONGODB_ATLAS_PASSWORD=<your_password>```. Make sure that your IP is in your database's whitelist IPs.
  3. **Nodemailer configuration**: Choose or create a gmail account and go to **Settings > Security > Recovery phone/Recovery email**, choose **Mail** and **Mac** to select the app and device you want to generate the password for and finally in the ```.env``` file add ```CONTACT_EMAIL=<your_email``` and ```PASSWORD_EMAIL=<generated_password>```
  4. **Auth secrets configuration**: Execute the following commands on your terminal to generate a secret for authorization processes:
      ```bash
        $ node
        $ require('crypto').randomBytes(64).toString('hex')
      ```
      Now, copy and paste the generated string in the ```.env``` file as follows ```AUTH_TOKEN_SECRET=<generated_string>```.

To configurate frontend you will need a [Syncfusion license](https://www.syncfusion.com). Once you have one, go to ```TFG-frontent/src/environments/environment.ts``` and add ```SYNCFUSION_LICENSE=<license>```

Finally, execute these commands on your terminal from TFG/ directory:
```bash
$ docker-compose build
$ docker-compose up
```

Now, you will be able to access to the platform through ```localhost:4200```
___
## Documentation 📖
Project's documentation can be found [here](https://github.com/ins426/TFG/tree/main/Memoria). In order to generate documentation in PDF format run the following commands on your terminal:
```bash
$ git clone git@github.com:ins426/TFG.git
$ cd TFG/Memoria
$ pdflatex proyecto.tex
```
[Used LaTeX template](https://github.com/JJ/plantilla-TFG-ETSIIT)
