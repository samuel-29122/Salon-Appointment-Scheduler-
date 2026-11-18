Salon Appointment Scheduler

A command-line appointment booking system for a salon, built with Bash and PostgreSQL. Built as part of the freeCodeCamp Relational Database certification.

What it does
Shows a numbered list of salon services pulled from the database
Lets a customer pick a service, and shows the list again if the choice doesn't exist
Looks up the customer by phone number, and asks for their name and saves them if they're new
Books the appointment at the customer's chosen time
Confirms the booking, e.g. I have put you down for a cut at 10:30, Fabio.
Tech used
Bash: the interactive script (salon.sh)
PostgreSQL: the database (salon.sql)
Database design
Table	Columns
customers	customer_id (primary key), phone (unique), name
services	service_id (primary key), name
appointments	appointment_id (primary key), customer_id (foreign key → customers), service_id (foreign key → services), time

Every primary key auto-increments, and appointments link to customers and services through foreign keys.

How to run it
Rebuild the database from the dump:
bash
psql -U postgres < salon.sql
Make the script executable:
bash
chmod +x salon.sh
Run it:
bash
./salon.sh
Example
~~~~~ MY SALON ~~~~~

Welcome to My Salon, how can I help you?

1) cut
2) color
3) perm
4) style
5) trim
1

What's your phone number?
555-555-5555

I don't have a record for that phone number, what's your name?
Fabio

What time would you like your cut, Fabio?
10:30

I have put you down for a cut at 10:30, Fabio.
Files
salon.sh: the appointment booking script
salon.sql: a database dump that rebuilds the salon database
What I learned
Designing related tables with primary and foreign keys
Querying PostgreSQL from a Bash script
Handling user input, validation and branching logic in Bash
