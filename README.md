# irhamramadhan
quismobile2
import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  Widget build(BuildContext context) {
    return MaterialApp(
      routes: {
        "/Add Business": (contex) => HalAddBusiness(),
        "/Add Call": (contex) => HalCall(),
        "/Add Chart": (contex) => HalChart(),
      },
      debugShowCheckedModeBanner: false,
      home: Scaffold(
        appBar: AppBar(
          title: Text('Menu'),
        ),
        body: GridView.count(
          crossAxisCount: 2,
          children: <Widget>[
            Menu(menu: "Add Business", picture: Icons.add_business),
            Menu(menu: "Add Call", picture: Icons.add_call),
            Menu(menu: "Add Chart", picture: Icons.add_chart),
          ],
        ),
      ),
    );
  }
}

class Menu extends StatelessWidget {
  final String menu;
  final IconData picture;

  Menu({this.menu, this.picture});

  Widget build(BuildContext context) {
    return Card(
      margin: EdgeInsets.all(8.0),
      child: InkWell(
        onTap: () {
          Navigator.pushNamed(context, "/$menu");
        },
        splashColor: Colors.purple,
        child: Center(
          child: Column(
            mainAxisSize: MainAxisSize.min,
            children: <Widget>[
              Icon(picture, size: 70.0),
              Text(menu, style: new TextStyle(fontSize: 17.0))
            ],
          ),
        ),
      ),
    );
  }
}

class HalAddBusiness extends StatelessWidget {
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text("Add Business"),
      ),
      body: Center(
        child: Column(
          children: [
            Icon(Icons.add_business_sharp, size: 75.0),
            Text('Business', style: new TextStyle(fontSize: 17.0))
          ],
        ),
      ),
    );
  }
}

class HalCall extends StatelessWidget {
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text("Add Call"),
      ),
      body: Center(
        child: Column(
          children: [
            Icon(Icons.add_call , size: 75.0),
            Text('Photo Collection',style: new TextStyle(fontSize: 17.0))],
        ),
      ),
    );
  }
}

class HalChart extends StatelessWidget {
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text("Add Chart"),
      ),
      body: Center(
        child: Column(
          children: [
            Icon(Icons.add_chart , size: 75.0),
            Text('Add Chart', style: new TextStyle(fontSize: 17.0))
          ],
        ),
      ),
    );
  }
}
