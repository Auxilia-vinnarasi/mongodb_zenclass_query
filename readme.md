1.Find all the topics and tasks which are thought in the month of October:

**db.zendb.find({$or:[{"topics.month":"october"},{"tasks.month":"october"}]},{"topics.topicsCovered":1,"tasks.taskList":1});**

2.Find all the company drives which appeared between 15 oct-2020 and 31-oct-2020:

**db.zendb.find({"companyDrives.Date":{"$gte":"15-oct-2020","$lte":"31-oct-2020"}},{"companyDrives.company_name":1});**

3.Find all the company drives and students who are appeared for the placement:

**db.zendb.find({},{username:1,"companyDrives.company_name":1});**

4.Find the number of problems solved by the user in codekata:

**db.zendb.find({},{"username":1,"codekata.problemsDone":1}).pretty();**

5.Find all the mentors with who has the mentee's count more than 15:

**db.zendb.find({"mentor.MenteesCount":{"$gt":15}},{"mentor.mentorName":1,"mentor.MenteesCount":1});**

6.Find the number of users who are absent and task is not submitted  between 15 oct-2020 and 31-oct-2020:

**db.zendb.find({"$and":[{"attendance":false},{"tasks.submittion":false},{"tasks.submittionDate":{"$gte":"15-oct-2020","$lte":"31-oct-2020"}}]}).count();**
