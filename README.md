# sallray-managment-system-using-flutter
Salary management system 

import 'package:flutter/material.dart';

void main() => runApp(SalaryManagementApp());

class SalaryManagementApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Salary Management System',
      theme: ThemeData(
        primarySwatch: Colors.blue,
        visualDensity: VisualDensity.adaptivePlatformDensity,
      ),
      home: SalaryManagementScreen(),
    );
  }
}

class SalaryManagementScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Salary Management System'),
      ),
      body: Padding(
        padding: EdgeInsets.all(16.0),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.stretch,
          children: [
            Text(
              'Employee List',
              style: TextStyle(
                fontSize: 24.0,
                fontWeight: FontWeight.bold,
              ),
            ),
            Expanded(
              child: ListView.builder(
                itemCount: 10, // Replace with actual number of employees
                itemBuilder: (BuildContext context, int index) {
                  return Card(
                    elevation: 2.0,
                    child: ListTile(
                      title: Text('Employee Name $index'),
                      subtitle: Text('Salary: \$5000'), // Replace with actual salary
                      trailing: IconButton(
                        icon: Icon(Icons.edit),
                        onPressed: () {
                          _editEmployee(context, index); // Implement edit functionality
                        },
                      ),
                    ),
                  );
                },
              ),
            ),
            ElevatedButton(
              onPressed: () {
                _addEmployee(context); // Implement add employee functionality
              },
              child: Text('Add Employee'),
            ),
          ],
        ),
      ),
    );
  }

  void _editEmployee(BuildContext context, int index) {
    // Implement edit functionality
    // You might use Navigator.push to navigate to a new screen for editing
  }

  void _addEmployee(BuildContext context) {
    // Implement add employee functionality
    // You might use Navigator.push to navigate to a new screen for adding
  }
}

