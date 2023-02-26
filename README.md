<a name="readme-top"></a>

<!-- TABLE OF CONTENTS -->
<details>V
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li><a href="#erdiagram">E-R Diagram</a><li>
      
    <li>
      <a href="#Create Tables">Create Tables</a>
      <ul>
        <li><a href="#Room">Room</a></li>
        <li><a href="#Sweeper">Sweeper</a></li>
        <li><a href="#Student">Student</a></li>
        <li><a href="#Cleaning Slots">Cleaning Slots</a></li>
        <li><a href="#Request">Request</a></li>
        <li><a href="#Cleaning Record">Cleaning Record</a></li>
      </ul>
    </li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
### About The Project

To build and update Room Cleaning Data for our hostel with mysql. To fetch the complicated query from database. 

Here's why:
* Data redundancy and inconsistency: The file system cannot control the redundancy of data as each user defines and maintains the needed files for a specific application to run.Whereas DBMS controls redundancy by maintaining a single repository of data that is defined once and is accessed by many users.
* Data concurrency: Concurrent access to data means more than one user is accessing the same data at the same time. Anomalies occur when changes made by one user get lost because of changes made by another user. The file system does not provide any procedure to stop anomalies. Whereas DBMS provides a locking system to stop anomalies to occur.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Built With

This section should list any major frameworks/libraries used to bootstrap your project. Leave any add-ons/plugins for the acknowledgements section. Here are a few examples.

*[![My_SQL][MYSQL]][Mysql-url]

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### erdiagram
![E-R Diagram](https://github.com/Sarvagy-Jain/Hostel-Room-Cleaning-Management-/blob/main/E-R_Diagram.png?raw=true)

<!-- GETTING STARTED -->
### Create Tables

<p align="center">
  <img src="[https://github.com/Sarvagy-Jain/Hostel-Room-Cleaning-Management-/blob/main/E-R_Diagram.png]" width="350" title="hover text">
</p>

### Room
```sh
Create table Room(
Room_No Number(10) constraint R_key Primary key,
Last_clean DATE
);
  
```

### Sweeper
```sh
Create table Sweeper(
Sweep_Id Number(10) constraint S_Id Primary key,
Sweep_Name Char(20)
);
  ```

### Student
  ```sh
  Create table Student(
  Roll_No Number(10) constraint Stu_Id Primary Key,
  Room_No Number(10) references Room(Room_No),
  Name Char(20) ,
  Phone_No Number(13),
  Allotment_Date Date
  );
  ```
  
### Cleaning Slots
  ```
  Create table Slot(
  Slot_Id Number(10) constraint Slot_Id Primary Key,
  Time Date 
  );
  ```

### Request
```
Create table Request 
(
Request_Id Number(10) constraint Req_Id Primary Key,
Roll_No Number(10) references Student(Roll_No),
Room_No Number(10) references Room(Room_No),
Slot_Id Number(10) references Slot(Slot_Id),
Request_Date Date
);
```

### Cleaing Record
```
Create table Clean  
(
Request_Id Number(10) references Request(Request_Id) ,
Room_No Number(10) references Room(Room_No),
Sweep_Id Number(10) references Sweeper(Sweep_Id),
Rating Number(1) default 0,
Primary Key(Request_Id)
);
```

<p align="right">(<a href="#readme-top">back to top</a>)</p>
<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".
Don't forget to give the project a star! Thanks again!

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE.txt` for more information.

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- CONTACT -->
## Contact

Your Name - [SARVAGY JAIN](https://www.linkedin.com/in/sarvagy-jain-17a74a207/) - sarvagyjain@gmail.com

Project Link: [https://github.com/Sarvagy-Jain/Hostel-Room-Cleaning-Management-](https://github.com/Sarvagy-Jain/Hostel-Room-Cleaning-Management-)

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- ACKNOWLEDGMENTS -->
## Acknowledgments



<p align="right">(<a href="#readme-top">back to top</a>)</p>


<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[MYSQL]:https://img.shields.io/badge/mysql-%2300f.svg?style=for-the-badge&logo=mysql&logoColor=white
[Mysql-url]: https://www.mysql.com/

