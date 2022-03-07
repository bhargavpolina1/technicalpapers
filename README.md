# SQL
**SQL** stands for **Structured Query Language**.
SQL is used to perform operations on **Relational DBMS**, where is stored in the form of tables.


## Create Table:
**CREATE** clause is used to create a new table in the database.
	
	Eg:
	   CREATE TABLE player (
  	   	name VARCHAR(200),
           	age INTEGER,
           	score INTEGER
           	);

## Inserting Rows:
**INSERT** clause is used to insert new rows in a table.
	
	Eg:
	 INSERT INTO
  	  player (name, age, score)
	 VALUES
  	  ("Rakesh", 39, 35),
  	  ("Sai", 47, 30);

## Retrieving Data:
**SELECT** clause is used to retrieve rows from a table. 
	
	Eg:
	 SELECT * 
	 FROM player
## Selecting Specific Rows:
**WHERE** clause is used to retrieve only specific rows. 
	
	Eg:
	  SELECT * 
	  FROM player 
	  WHERE name="Sai";
	
## Update Rows:

 **UPDATE** clause is used to update the data of an existing table in database. 
	We can update all the rows or only specific rows using WHERE clause as per the requirement.
	
## Update All Rows:
   Eg:
	  UPDATE
  	   player
	  SET
       score = 100;
	
	Update Specific Rows:
	  UPDATE
  	    player
	   SET
  	    score = 150
	   WHERE
  	    name = "Ram";

Delete Rows:

	DELETE clause is used to delete existing records from a table.
	
	Delete All Rows:
	 DELETE FROM
  	  player;
	
	Delete Specific Rows:
	 DELETE FROM
  	  player
	 WHERE
  	  name = "Shyam";
Drop Table:
	DROP clause is used to delete a table from the database.
	Eg:
	   DROP TABLE player;

Alter Table:
	ALTER clause is used to add, delete, or modify columns in an existing table.
	
	Add Column:
	  ALTER TABLE
  	  player
	 ADD
  	  jersey_num INT;
	
	Rename Column:
	  ALTER TABLE
  		player RENAME COLUMN jersey_num TO jersey_number;
	Drop Column:
	  ALTER TABLE
  		player DROP COLUMN jersey_number;

JOINS:
	JOIN clause is used to combine rows from two or more tables, based on a related column between them. 
	There are various types of joins, namely Natural join, Inner Join, Full Join, Cross Join, Left join, Right join.
	
	Natural JOIN:
		NATURAL JOIN combines the tables based on the common columns.
		
		Eg:
		  SELECT course.name,
  			instructor.full_name
		  FROM course
  		  NATURAL JOIN
			instructor
             WHERE instructor.full_name = "Alex";
             
	INNER JOIN:
		INNER JOIN combines rows from both the tables if they meet a specified condition.
		
		Eg:
		  SELECT student.full_name,
   		   review.content,
   		   review.created_at
		FROM student
   		INNER JOIN review 
		ON student.id = review.student_id
		WHERE review.course_id = 15;
	LEFT JOIN:
		In LEFT JOIN, for each row in the left table, matched rows from the right table are combined. 
		If there is no match, NULL values are assigned to the right half of the rows in the temporary table.
		
		Eg:
		  SELECT student.full_name
		  FROM student
   		  LEFT JOIN student_course
		  ON student.id = student_course.student_id
		  WHERE student_course.id IS NULL;
	RIGHT JOIN:
		RIGHT JOIN or RIGHT OUTER JOIN is vice versa of LEFT JOIN.
		I.e., in RIGHT JOIN, for each row in the right table, matched rows from the left table are combined. 
		If there is no match, NULL values are assigned to the left half of the rows in the temporary table.
		
		Eg:
		  SELECT course.name,
    			instructor.full_name
		  FROM course
   		  RIGHT JOIN instructor
                  ON course.instructor_id = instructor.instructor_id;

	FULL JOIN:
		FULL JOIN or FULL OUTER  JOIN is the result of both RIGHT JOIN and LEFT JOIN.
		
		Eg:
		  SELECT course.name,
    		  instructor.full_name
		  FROM course
                  FULL JOIN instructor
  		  ON course.instructor_id = instructor.instructor_id;
	CROSS JOIN:
		In CROSS JOIN, each row from the first table is combined with all rows in the second table. 
		Cross Join is also called as CARTESIAN JOIN.
		Eg:
		  SELECT course.name AS course_name,
    		   instructor.full_name AS instructor_name
		  FROM course
   		  CROSS JOIN instructor;
       SELF JOIN:
		We can also combine a table with itself. This kind of join is called SELF-JOIN.
		
		Eg:
		  SELECT t1.c1,
   		  t2.c2
		  FROM table1 AS t1
   		  JOIN table1 AS t2
		  ON t1.c1 = t2.cn;
Aggregation:
	Combining multiple values into a single value is called aggregation.
	Aggregate Functions:
		I)COUNT: Counts the number of values
		
			Eg:
 		 	 SELECT COUNT()    
 		 	 FROM player_match_details;
		
		II)SUM: Adds all the values
		
			Eg:
		 	  SELECT
  		 	  SUM(score)
		 	  FROM
  		  	  player_match_details
		 	  WHERE
  		  	   name = "Ram";
		
		III)MIN: Returns the minimum value
			
			Eg:
			SELECT
  			MIN(score)
			FROM
  			 player_match_details
			WHERE
  			 year = 2011;
		IV)MAX: Returns the maximum value
			
			Eg:
			SELECT
  			MAX(score)
			FROM
  			 player_match_details
			WHERE
  			 year = 2011;
		V)AVG: Calculates the average of the values
			Eg:
			SELECT
  			AVG(score)
			FROM
  			 player_match_details
			WHERE
  			 year = 2011;
		

			
			
			
			
		
		



	 
	  
