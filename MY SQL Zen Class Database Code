create database Zen_Class_Database;

use Zen_Class_Database;

create table users(
user_id int primary key,
username varchar(255) not null,
email varchar(50) not null unique,
password varchar(20) not null,
role varchar(255),
createdAt datetime default now(),
updated_at datetime
);
create table students(
student_id int primary key,
user_id int not null,
full_name varchar(255) not null,
address text not null,
phone_number varchar(10) not null,
qualification text not null,
work_experience text not null
);
create table mentors(
mentor_id int primary key,
user_id int not null,
full_name varchar(255) not null,
address text not null,
phone_number varchar(255) not null,
qualification text not null,
work_experience text not null
);
create table topics (
  topic_id int primary key,
  topic_name varchar(255),
  description text,
  num_sessions int,
  mentor_id int
);
create table task(
task_id int primary key,
  topic_id int,
  task_name varchar(255),
  description text not null,
  deadline date
);
create table attendance(
attendance_id int primary key,
  user_id int not null,
  topic_id int not null,
  session_date date,
  status varchar(255)
);

create table capstone(
capstone_id int primary key,
  user_id int not null,
  project_name varchar(255),
  description text
);
create table queries(
query_id int primary key,
  student_id int unique,
  mentor_id int unique not null,
  topic_id int unique not null,
  question varchar(255) unique not null,
  answer text
);
create table portfolio_submission (
  submission_id int primary key,
  student_id int,
  capstone_id int,
  submission_date date,
  github_url varchar(255),
  portfolio_url varchar(255),
  resume_url varchar(255)
);


ALTER TABLE `students` ADD FOREIGN KEY (`user_id`) REFERENCES `users` (`user_id`);
ALTER TABLE `mentors` ADD FOREIGN KEY (`user_id`) REFERENCES `users` (`user_id`);
ALTER TABLE `topics` ADD FOREIGN KEY (`mentor_id`) REFERENCES `mentors` (`mentor_id`);
ALTER TABLE `task` ADD FOREIGN KEY (`topic_id`) REFERENCES `topics` (`topic_id`);
ALTER TABLE `attendance` ADD FOREIGN KEY (`user_id`) REFERENCES `users` (`user_id`);
ALTER TABLE `attendance` ADD FOREIGN KEY (`topic_id`) REFERENCES `topics` (`topic_id`);
ALTER TABLE `capstone` ADD FOREIGN KEY (`user_id`) REFERENCES `users` (`user_id`);
ALTER TABLE `queries` ADD FOREIGN KEY (`student_id`) REFERENCES `students` (`student_id`);
ALTER TABLE `queries` ADD FOREIGN KEY (`mentor_id`) REFERENCES `mentors` (`mentor_id`);
ALTER TABLE `queries` ADD FOREIGN KEY (`topic_id`) REFERENCES `topics` (`topic_id`);
ALTER TABLE `portfolio_submission` ADD FOREIGN KEY (`student_id`) REFERENCES `students` (`student_id`);
ALTER TABLE `portfolio_submission` ADD FOREIGN KEY (`capstone_id`) REFERENCES `capstone` (`capstone_id`);


