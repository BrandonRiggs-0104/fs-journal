# A bit more CSharp and SQL
1. What does ***inheritance*** accomplish for us in C#?

  > | Creates a new class from an already existing class.

2. How does ***member inheritance*** work in C#? Does a `Class` inherit all members of the base `Class`?

  > | Defines a child class to reuse extends, or modifies the parent.
  no they dont.

3. How does ***accessibility*** affect inheritance?

  > | Just changes who is allowed to access them.

4. What is the difference between a `PRIMARY KEY` and a `FOREIGN KEY`

  > | Primary key gives a unique identifier to everything in the table while foreign key is used to refrence something in a table from a different table.

5. What is an ***alias***?

  > | Lets you give a temporary name to a table or a column in that table.

6. Demonstrate how you would query a join statement that would get all of a doctors patients from the following collections:

  ```SQL
  CREATE TABLE doctors (
    id INT NOT NULL AUTO_INCREMENT,
    -- CODE OMITTED
    PRIMARY KEY (id)
  )

  CREATE TABLE patients (
    id INT NOT NULL AUTO_INCREMENT,
    -- CODE OMITTED
    PRIMARY KEY (id)
  )

  CREATE TABLE patient_doctors (
    id INT NOT NULL AUTO_INCREMENT,
    doctorId INT NOT NULL,
    patientId INT NOT NULL,

    FOREIGN KEY (doctorId)
      REFERENCES doctors(id),
    FOREIGN KEY (patientId)
      REFERENCES patients(id),
  )

  ```

  > | string sql = @" SELECT * FROM patients WHERE id = @patient_doctorsId;"; List patients = _db.Query<Doctors, Patients, Patients>(sql, (doctors, patient) => { patient.doctorId = patient.Id; return patient; }, new { doctorId }).ToList(); return patients; ";



  