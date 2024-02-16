import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'RemindMer',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      routes: {
        '/': (context) => GirisSayfasi(),
        '/home': (context) => HomePage(),
      },
    );
  }
}

class GirisSayfasi extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text(
          'RemindMer',
          style: TextStyle(
            fontSize: 40,
            color: Colors.lightGreen,
          ),
        ),
        backgroundColor: Colors.lightBlue,
      ),
      body: Center(
        child: Padding(
          padding: const EdgeInsets.all(20.0),
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: [
              TextField(
                decoration: InputDecoration(
                  labelText: 'User Name',
                ),
              ),
              TextFormField(
                decoration: InputDecoration(
                  labelText: 'Password',
                ),
                obscureText: true,
              ),
              SizedBox(height: 20),
              ElevatedButton(
                onPressed: () {
                  Navigator.pushReplacementNamed(context, '/home');
                },
                style: ElevatedButton.styleFrom(
                  primary: Colors.lightBlue,
                ),
                child: Text('Login'),
              ),
              TextButton(
                onPressed: () {
                  // Şifremi Unuttum butonuna basıldığında yapılacak işlemler
                },
                child: Text('Forgot My Password'),
              ),
            ],
          ),
        ),
      ),
    );
  }
}

class HomePage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('RemindMer'),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            ElevatedButton(
              onPressed: () {
                Navigator.push(
                  context,
                  MaterialPageRoute(builder: (context) => GorevlerSayfasi()),
                );
              },
              style: ElevatedButton.styleFrom(
                shape: CircleBorder(),
                padding: EdgeInsets.all(40),
                primary: Colors.green,
              ),
              child: Icon(
                Icons.add,
                size: 100,
              ),
            ),
          ],
        ),
      ),
    );
  }
}

class GorevlerSayfasi extends StatefulWidget {
  @override
  _GorevlerSayfasiState createState() => _GorevlerSayfasiState();
}

class _GorevlerSayfasiState extends State<GorevlerSayfasi> {
  Color lambaRenk = Colors.amber;
  Color suRenk = Colors.blue;
  Color prizRenk = Colors.green;
  Color kapiKilitRenk = Colors.red;
  String extraGorev = '';

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Tasks'),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            SizedBox(
              width: 200,
              height: 50,
              child: ElevatedButton(
                onPressed: () {
                  setState(() {
                    lambaRenk = Colors.white;
                  });
                },
                style: ElevatedButton.styleFrom(
                  primary: lambaRenk,
                ),
                child: Text('Lamp'),
              ),
            ),
            SizedBox(height: 20),
            SizedBox(
              width: 200,
              height: 50,
              child: ElevatedButton(
                onPressed: () {
                  setState(() {
                    suRenk = Colors.white;
                  });
                },
                style: ElevatedButton.styleFrom(
                  primary: suRenk,
                ),
                child: Text('Water'),
              ),
            ),
            SizedBox(height: 20),
            SizedBox(
              width: 200,
              height: 50,
              child: ElevatedButton(
                onPressed: () {
                  setState(() {
                    prizRenk = Colors.white;
                  });
                },
                style: ElevatedButton.styleFrom(
                  primary: prizRenk,
                ),
                child: Text('Socket'),
              ),
            ),
            SizedBox(height: 20),
            SizedBox(
              width: 200,
              height: 50,
              child: ElevatedButton(
                onPressed: () {
                  setState(() {
                    kapiKilitRenk = Colors.white;
                  });
                },
                style: ElevatedButton.styleFrom(
                  primary: kapiKilitRenk,
                ),
                child: Text('Door Lock'),
              ),
            ),
            SizedBox(height: 20),
            SizedBox(
              width: 200,
              height: 50,
              child: TextFormField(
                onChanged: (value) {
                  extraGorev = value;
                },
                decoration: InputDecoration(
                  labelText: ' ',
                  border: OutlineInputBorder(),
                ),
              ),
            ),
          ],
        ),
      ),
    );
  }
}

