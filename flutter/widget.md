Stateless Widgetの雛形

```dart
/* 画面の名前 */

import 'package:flutter/material.dart';

/* routerで渡される値 */
class EditStudentArgument {}


class WIDGETNAME extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text("appbar"),
        actions: <Widget>[],
      ),
      body: Text("data"),
      floatingActionButton: FloatingActionButton.extended(
        onPressed: null,
        label: null,
      ),
    );
  }
}

```