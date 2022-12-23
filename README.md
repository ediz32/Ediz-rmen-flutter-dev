import 'package:flutter/material.dart';

void main() {
  runApp(
    MaterialApp(
      home: MyApp(),
    ),
  );
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: Center(
        child: FittedBox(
          fit: BoxFit.contain,
          child: Image.asset('assets/my_image.png'),
        ),
      ),
    );
  }
}

import 'package:flutter/material.dart';

void main() {
  runApp(
    MaterialApp(
      home: MyApp(),
    ),
  );
}

class MyApp extends StatefulWidget {
  @override
  _MyAppState createState() => _MyAppState();
}

class _MyAppState extends State<MyApp> {
  bool _isVisible = true;

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: Center(
        child: Offstage(
          offstage: !_isVisible,
          child: Text('Hello World'),
        ),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: () {
          setState(() {
            _isVisible = !_isVisible;
          });
        },
        child: Icon(Icons.toggle_off),
      ),
    );
  }
}


import 'package:flutter/material.dart';

void main() {
  runApp(
    MaterialApp(
      home: MyApp(),
    ),
  );
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: Center(
        child: SizedBox(
          width: 100,
          height: 100,
          child: Container(
            color: Colors.red,
          ),
        ),
      ),
    );
  }
}

import 'package:flutter/material.dart';

void main() {
  runApp(
    MaterialApp(
      home: MyApp(),
    ), 
  );
}

class MyApp extends StatefulWidget {
  @override
  _MyAppState createState() => _MyAppState();
}

class _MyAppState extends State<MyApp> {
  final _formKey = GlobalKey<FormState>();

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: Form(
        key: _formKey,
        child: Column(
          children: [
            FormField(
              builder: (FormFieldState state) {
                return TextFormField(
                  validator: (value) {
                    if (value.isEmpty) {
                      return 'Please enter a value';
                    }
                    return null;
                  },
                );
              },
            ),
            RaisedButton(
              onPressed: () {
                if (_formKey.currentState.validate()) {
                  // Form is valid, do something here
                }
              },
              child: Text('Submit'),
            ),
          ],
        ),
      ),
    );
  }
}
