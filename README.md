# MIST4610-Group-Project-1
Team Name: 29704 1

# Team Members
1. Jillian Bolgla [@jillianbolgla](https://github.com/jillianbolgla)
2. Conor Dillon [@cjdillon11](https://github.com/cjdillon11)
3. Brandon Hopper [@bhop19](https://github.com/bhop19)
4. Neha Panchal [@nehapanchal2001](https://github.com/nehapanchal2001)
5. Shrija Ramachandran Ganesh Mohan - [@shrija-27](https://github.com/shrija-27)
6. Alvin Vasanthakumar - [@alvinvasanth](https://github.com/alvinvasanth)


# ChatGPT Response
https://docs.google.com/document/d/1RU8uZK5zfxMJaa5XlytWOYu2rA_4dH5KpP6m32WwGoM/edit?usp=sharing 

# Problem Description
We are tasked with creating a relational database and data model for the owner of a football club. In our model the central entity is the Club. Each club has teams that operate in different divisions and in various locations. The club operates in conjunction with matches, training sessions, ticket sales, etc. that it offers to fans who support the teams.We want to accurately model these relationships, generating sample data, and populating entities and queries with the sample data. Additionally, we are planning on performing functioning queries on this data so that they can provide us with valuable player and coach statistics as well as the overall club performance. 

# Data Model
Explanation of the data model: 

The data model that was created is based on a theoretical football club. The Teams entity is a representation of all of the teams within the club (professional league, 16U, 12U, etc). Within the team, there are several players which are represented with one to many relationships between the Teams and Players entities. Hence, there are several players that belong to a single team. These players also have many stats as a result of the games they participate in. For example, their overall rating, number of goals scored, number of pass attempts, their position rating and so on. Therefore, this is represented with a one to many relationship between the Players and Stats entity. Additionally, Teams also have many coaches but a coach may only instruct one team at a time. For that reason, a one to many relationship between the Teams and Coaches entity was created.  

There are also many matches that a team may play and matches may be played by many teams, which is why there is a many to many relationship between Teams and Matches. As a result we created an associative entity labeled Matchup. This entity stores information when two teams are playing each other within a game. For example, the table allows users to see what teams are playing and the number of goals scored by both the team and opponent. Subsequently, matches require tickets for individuals to attend. A one to many relationship was placed between Matches and Tickets due to the fact that a match has several tickets for individuals to attend. 

There are also many training schedules that a team may have so we established an entity called TrainingSchedules. This is a one to many relationship between Teams and TrainingSchedules. 

On the other end of our data model we have the relationships between the Team and its corresponding fans and sponsors. The first relationship is one between Teams and Fans. This is a many to many relationship due to the fact that teams can have many fans supporting them and fans can support more than one team at a time. As a result, an associative entity was created labeled Fanbase, which stores information regarding who the fan is and what teams they support. Secondly, the relationship between Teams and Sponsors was created as a many to many relationship. Teams can have many sponsors while sponsors can sponsor several teams.  Therefore, another associative entity was created which stores information regarding the team and sponsor which was given the title Funding. 

Lastly, there is a Club entity created that represents the club associated with the respective teams. This entity, Club, stores information about the club name, description, and specific ID. There are 3 relationships associated with the Club entity. First, we created a one to many relationship with the Facilities entity since clubs can have access to several facilities. Secondly, a one to many relationship was created with the Transactions entity. A club can have several transactions such as rent, utilities, supplies, etc. Finally, the relationship between Club and Teams was created as a one to many relationship. There is one club, Georgia United FC, that houses all of the teams associated with the Club. However, a team may only belong to one club, Georgia United FC. 

![image](https://github.com/nehapanchal2001/MIST-4610-Project-1/assets/148079624/e238cfc2-4c4d-4e20-adba-931ea98b1ddc)

# Data Dictionary 

![image](https://github.com/nehapanchal2001/MIST-4610-Project-1/assets/148079624/e40a4be3-a912-4737-9ffc-ae83ecdda867)

![image](https://github.com/nehapanchal2001/MIST-4610-Project-1/assets/148079624/53d84ab3-5188-4fb3-9c90-212aa09b67e4)

![image](https://github.com/nehapanchal2001/MIST-4610-Project-1/assets/148079624/859b4134-a10e-427f-a5d6-dc75473850d7)

![image](https://github.com/nehapanchal2001/MIST-4610-Project-1/assets/148079624/d2997698-b868-4b25-945a-e44d6b27a78c)

![image](https://github.com/nehapanchal2001/MIST-4610-Project-1/assets/148079624/65894cb4-4050-4aad-9229-29af97ace5e2)

![image](https://github.com/nehapanchal2001/MIST-4610-Project-1/assets/148079624/936dd01a-9b45-49dd-80bf-33dc80a1be7c)

![image](https://github.com/nehapanchal2001/MIST-4610-Project-1/assets/148079624/d13448b1-8608-4b08-83a6-809c0a5cbf2a)

![image](https://github.com/nehapanchal2001/MIST-4610-Project-1/assets/148079624/9a4e3c74-6cea-412f-b719-b3b184147660)

![image](https://github.com/nehapanchal2001/MIST-4610-Project-1/assets/148079624/39624569-4248-4608-b82b-9a5b6d1d0c5f)

![image](https://github.com/nehapanchal2001/MIST-4610-Project-1/assets/148079624/afa2d763-7dcc-4a87-810b-8900847afbaf)

![image](https://github.com/nehapanchal2001/MIST-4610-Project-1/assets/148079624/211bfce2-565f-4648-b8e1-eea6eef2e001)

![image](https://github.com/nehapanchal2001/MIST-4610-Project-1/assets/148079624/338e27ce-dedd-4375-81ce-fd524ede20a7)

![image](https://github.com/nehapanchal2001/MIST-4610-Project-1/assets/148079624/f5000378-b932-4e9a-8f75-aa95d589eed8)

![image](https://github.com/nehapanchal2001/MIST-4610-Project-1/assets/148079624/9a8a5a83-6d6c-4da1-8f38-061fe06e6433)

![image](https://github.com/nehapanchal2001/MIST-4610-Project-1/assets/148079624/843abf3f-19c0-47dc-8e7e-cd0ac0ef32bf)

# SQL Queries

**TP_Q1**: Write a query that lists all the players and their positons
![image](https://github.com/nehapanchal2001/MIST-4610-Project-1/assets/148079624/26dd4fd7-c594-411f-9f5f-eecedbb2a23c)
Explanation: Knowing the list of players and their positions can have tactical, strategic, and managerial reasons. This list can be of interest to stakeholders, coaches and talent scouts to fans. 

**TP_Q2**: Write a query that lists what fans have attended more than 50 matches. Order the number of matches attended from least to greatest.
![image](https://github.com/nehapanchal2001/MIST-4610-Project-1/assets/148079624/caffa4c1-e373-49c8-b8f9-5dbb96bc4290)
Explanation: Marketing is essential to creating a strong fanbase. A manager might want to know how many fans have attended a certain amount of games to see loyalty. Having loyal fan feedback and input can help improve experiences, player performance, marketing data, and build a sense of community between the players and fans.

**TP_Q3**: Write a query that lists the total amount paid for each transaction type.
![image](https://github.com/nehapanchal2001/MIST-4610-Project-1/assets/148079624/ae7577f1-eb9b-4245-80d5-f4be60272c6e)
Explanation: A manager would want to know the total amount paid since it’s essential for financial analysis and make informed decisions about where to allocate revenues and control costs if over budget

**TP_Q4**: list out each matchup that resulted in a Georgia United FC victory
![image](https://github.com/nehapanchal2001/MIST-4610-Project-1/assets/148079624/a6cf8bf8-0cd0-4ab8-af9b-d33cccdd703e)
Explanation: Knowing the list of matchups that resulted in a Georgia United FC victory can be valuable reasons such as performance analysis where the coaches can identify strong strategies, team performance and player strength/weaknesses. A list can help coaches/managers go through each game to make future game plans for a victory.

**TP_Q5**: List the name of each coach, their specialty, and what team they belong to. Order the results in descending order for team name and coach speciality. 
![image](https://github.com/nehapanchal2001/MIST-4610-Project-1/assets/148079624/2ee00330-3239-427f-a990-f29976c1ec1b)
Explanation: A club manager would want to know the specific details of all the coaches that they employ. It is essential to keep track of coach details such as their speciality and the team they are associated with to perform thorough performance evaluations and track their success. 

**TP_Q6**: List the sponsor name and contact information for those sponsors whose payment is greater than the average payment
![image](https://github.com/nehapanchal2001/MIST-4610-Project-1/assets/148079624/934657de-ffbe-4513-a4f3-753f88e33386)
Explanation: Keeping track of sponsors is a key component of a club because they provide a significant amount of funding to keep the club running. Monitoring sponsors ensures that the manager is aware of the financial commitments and support provided by sponsors. Sponsors who contribute amounts greater than the average payment should be noted as higher level sponsors and recognized by the manager. 

**TP_Q7**: List the different teams, their coaches who specialize in defense, and the players whose position is defense
![image](https://github.com/nehapanchal2001/MIST-4610-Project-1/assets/148079624/2935dce0-3b7a-42f3-a81f-3aef2aba27fe)
Explanation: Defense is an important aspect of any sport. This query allows for managers and coaches to have accessible data for the players who play defense and the coaches that specialize in defense. Having this information can be useful when managers are looking at their roster assessing the makeup of each team.

**TP_Q8**:Write a query that lists each player and their skill level, determined by their overall rating. Order the results by 'talent level.'
![image](https://github.com/nehapanchal2001/MIST-4610-Project-1/assets/148079624/d0c9d8b3-5c64-451b-8f4f-21082d1205af)
Explanation: Player performance is critical in a team's success. This query allows managers and coaches to see how players are performing based on their overall rating. Coaches and managers can see what players need more practice and can use that to better equip their teams for success. 

**TP_Q9**: Write a query to list out players for ____ (specific team) who make more than ____ (certain amount so we can use the having clause). Order the results in descending order.
![image](https://github.com/nehapanchal2001/MIST-4610-Project-1/assets/148079624/99180db5-6adf-46a3-907f-18ba632b988f)
Explanation: Salary is a huge component of teams, however teams only have so much money they can hand out. Therefore, this query allows managers to evaluate how their budget is being allocated. It’s important to note that managers can input any team name and any salary depending on their needs. We used the team “Lions” and the salary “$200,000” as an example.

**TP_Q10**: Write a query to list out average price of tickets that are ____ (certain ticket type) where the match opponent was ______ (certain match opponent)
![image](https://github.com/nehapanchal2001/MIST-4610-Project-1/assets/148079624/895bb329-99c5-49c7-86b5-c2c6c74ded1a)
Explanation: This query allows the club executives and high level managers to see which type of seats are being sold out in accordance with which match opponents are playing in order to gain a better understanding of where people desire to watch their favorite teams play. This helps them not only to structure their stadium seats to gain more viewership profit, but also see how the pricing of tickets is being affected by which teams play. With this information, they can see which teams playing against each other elicit higher ticket prices, and create matchups for better profit. Again, it is important to note that managers can input any type of seat and opponent they choose, adding flexibility for the managers. We chose Box seats and Franecki-O’Reilly for purposes of output.

# Queries Chart: 
![image](https://github.com/nehapanchal2001/MIST-4610-Project-1/assets/148079624/6cf95426-a325-42d2-82be-63ec14174fb4)


# Database information:
Name of the database: ns_29704_1

Additional information: Each query listed above is marked in the database using stored procedures which can be called using the following format: CALL TP_Q1();
