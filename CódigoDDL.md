## Código DDL:

  ```
CREATE TABLE member (

id SERIAL PRIMARY KEY,

fullname VARCHAR(100),

email VARCHAR(100) UNIQUE,

age INT

);

CREATE TABLE event (

id SERIAL PRIMARY KEY,

description TEXT,

start_date DATE,

end_date DATE,

total_attendees INT,

city VARCHAR(100)

);

CREATE TABLE conference (

id SERIAL PRIMARY KEY,

title VARCHAR(100),

speaker VARCHAR(100),

hour TIME,

day DATE,

total_attendees INT,

event_id INT REFERENCES event(id)

);

CREATE TABLE register (

id SERIAL PRIMARY KEY,

member_id INT REFERENCES member(id) UNIQUE,

conference_id INT REFERENCES conference(id) UNIQUE,

code VARCHAR(20),

registered_at TIMESTAMP,

assisted BOOLEAN

);
  ```

