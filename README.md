# SEA8 - Spring Data JPA Quest 02 - One-to-Many

## Challenge: The magic of Spring Data JPA

*Fork* the following repository: https://github.com/WCS-Java-Training-Bonn-2019/quest-spring-jpa-manytomany.

You are taking over the development of a Harry Potter fan site to add the following features:

- a wizard should be able to register for one or more classes and view them all.
- it should be possible to retrieve the list of students enrolled in a course.

The first step will be to create the database *spring_jpa_manytomany* from **this sql file**:

```
curl -s https://raw.githubusercontent.com/WildCodeSchool/quest-spring-jpa-manytomany/master/database/spring_jpa_manytomany.sql | mysql -u root -p
```

The user is the same as in the previous quests: *h4rryp0tt3r* with the same password as before: *Horcrux4life*.
It will be necessary to give this user all permissions over the database called *spring_jpa_manytomany*:

```SQL
GRANT ALL PRIVILEGES ON spring_jpa_manytomany.* TO 'h4rryp0tt3r'@'localhost';
```

1. Modify the entity *Wizard* and add the code that is required to create the relationship with a list of multiple courses: *List<Course> courses*.
2. *Wizard* should be considered the "master" in the relationship and the join table will be called: *wizard_course*.
3. Modify the entity *Course* and add the code that would be required to create the relationship with a list of multiple student wizards: *List<Wizard> wizards*
4. Restart the server: you should see the requests to create the join table, the foreign keys and their constraints in the *logs*
5. It should be possible to enroll a student in courses and view their schedule without modifying any other classes, and likewise to see the student register for any given class, via the "courses" route.

If it doesn't work, check the error messages in the *logs*:

- did you name the attributes correctly as requested?
- did you create the *getters* and *setters*?

## Validation criterias

- The project runs correctly using the required database and user details.
- The class *Wizard* contains all the code necessary to return a list of courses.
- The class *Course* contains all the code necessary to return a list of wizards.
- It is possible for a student to register for one or more courses from the "courses" route.
- It is possible to see a student's list of courses from the "register" link.
- The code is available on GitHub.
