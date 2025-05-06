import 'package:flutter/material.dart';

void main() => runApp(CustomFABApp());

class CustomFABApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(home: FABDemoPage());
  }
}

class FABDemoPage extends StatelessWidget {
  void _onFabPressed() {
    print("Custom FAB Pressed!");
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text("Custom FAB Example")),
      body: Stack(
        children: [
          Center(child: Text("Main Content")),
          
          // Custom FAB Positioned in bottom-right
          Positioned(
            bottom: 20,
            right: 20,
            child: InkWell(
              onTap: _onFabPressed,
              borderRadius: BorderRadius.circular(30),
              child: Container(
                width: 60,
                height: 60,
                decoration: BoxDecoration(
                  color: Colors.purple,
                  shape: BoxShape.circle,
                  boxShadow: [
                    BoxShadow(
                      color: Colors.black26,
                      blurRadius: 10,
                      offset: Offset(2, 4),
                    )
                  ],
                ),
                child: Icon(Icons.add, color: Colors.white, size: 30),
              ),
            ),
          ),
        ],
      ),
    );
  }
}
