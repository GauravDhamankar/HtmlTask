# HtmlTask

<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet"
        integrity="sha384-T3c6CoIi6uLrA9TneNEoa7RxnatzjcDSCmG1MXxSR1GAsXEV/Dwwykc2MPK8M2HN" crossorigin="anonymous" />
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js"
        integrity="sha384-C6RzsynM9kWDrMNeT87bh95OGNyZPhcTNXj1NW7RuBCsyN/o0jlpcV8Qyq46cDfL"
        crossorigin="anonymous"></script>
</head>

<body>


    <div class="container-fluid">
        <div class="row">
            <div id="empDetails"></div>
        </div>
    </div>

    <script>

        window.onload = function () {
            console.log('Hello World');
        }

        let objArray = [
            {
                fname: 'Gaurav',
                lname: 'Dhamankar',
                age: 23,
                salary: 25000,
                role: 'Software Engineer',
                action: `<button class="btn bg-success" onclick="addData()">Add</button> <button class="btn bg-danger">Delete</button>`
            },
            {
                fname: 'Rohit',
                lname: 'Chavan',
                age: 22,
                salary: 23000,
                role: 'QA Engineer',
                action: `<button class="btn bg-success" onclick="addData()">Add</button> <button class="btn bg-danger">Delete</button>`
            },
            {
                fname: 'Tejas',
                lname: 'Thorvat',
                age: 22,
                salary: 27500,
                role: 'Data Engineer',
                action: `<button class="btn bg-success" onclick="addData()">Add</button> <button class="btn bg-danger">Delete</button>`
            },
            {
                fname: 'Prashant',
                lname: 'Ajgekar',
                age: 22,
                salary: 23000,
                role: 'Design Engineer',
                action: `<button class="btn bg-success" onclick="addData()">Add</button> <button class="btn bg-danger">Delete</button>`
            }
        ];

        localStorage.setItem("key",JSON.stringify(objArray));

        function addData() {
            const fname = prompt('Enter first name');
            const lname = prompt('Enter last name');
            const age = prompt('Enter age');
            const salary = prompt('Enter salary');
            const role = prompt('Enter role');
            const action = `<button class="btn bg-success" onclick="addData()">Add</button> <button class="btn bg-danger">Delete</button>`

            let empObj = {
                fname: fname,
                lname: lname,
                age: age,
                salary: salary,
                role: role,
                action: action
            };

            // Adding emp obj to array
            objArray.push(empObj);

            localStorage.setItem("UserInfo", JSON.stringify(empObj));
        }

        

        // display data to table
        function displayIntotable(objArray) {
            let table = `<table class="table table-hover">`;
            table += `<thead>
                    <tr>
                        <th scope="row">First Name</th>
                        <th scope="row">Last Name</th>
                        <th scope="row">Age</th>
                        <th scope="row">Salary</th>
                        <th scope="row">Role</th>
                        <th scope="row">Action</th>
                    </tr>
                    </thead>`;

                    objArray.forEach((item, value)=>{
                        table += `<tr>`;
                        table += `<td>${item.fname}</td>`;
                        table += `<td>${item.lname}</td>`;
                        table += `<td>${item.age}</td>`;
                        table += `<td>${item.salary}</td>`;
                        table += `<td>${item.role}</td>`;
                        table += `<td>${item.action}</td>`;
                        table += `</tr>`;
                    });
                    table += `</table>`;
                    document.getElementById('empDetails').innerHTML = table ;
        }

        displayIntotable(objArray);


    </script>

    <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.11.8/dist/umd/popper.min.js"
        integrity="sha384-I7E8VVD/ismYTF4hNIPjVp/Zjvgyol6VFvRkX/vR+Vc4jQkC+hVqc2pM8ODewa9r"
        crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.min.js"
        integrity="sha384-BBtl+eGJRgqQAUMxJ7pMwbEyER4l1g+O15P+16Ep7Q9Q+zqX6gSbd85u4mG4QzX+"
        crossorigin="anonymous"></script>
</body>

</html>
