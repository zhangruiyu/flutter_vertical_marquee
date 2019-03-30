# flutter_vertical_marquee

[![pub package](https://img.shields.io/pub/v/flutter_vertical_marquee.svg)](https://pub.dartlang.org/packages/flutter_vertical_marquee)
## NOTE
  在作者的原始代码上修改了一下，可以指定内容是 居左/居右/居中


## screenshot

![image](https://raw.githubusercontent.com/CaiJingLong/some_asset/master/flutter_vertical_marquee1.gif)

yaml

```yaml
dependencies:
  flutter:
    sdk: flutter

  ...
  # marquee
  flutter_vertical_marquee:
    git:
      url: https://github.com/mimicode/flutter_vertical_marquee
```

import in dart:

```dart
import 'package:flutter_vertical_marquee/flutter_vertical_marquee.dart';
```

build widget

```dart
  List<String> _tipMarqueeList = [];

  _initMarquee() {
    _tipMarqueeList.clear();
    _tipMarqueeList.addAll(["test1", "test2"]);
  }

  Widget _buildMarquee() {
    _initMarquee();
    var controller = MarqueeController();
    return GestureDetector(
      child: Container(
        height: 40.0,
        color: Colors.lightBlueAccent.shade100,
        child: Marquee(
          aligment: MarqueeAligment.left,
          textList: _tipMarqueeList, // List<Text>, textList and textSpanList can only have one of code.
          textSpanList: // List<TextSpan> text, textList and textSpanList can only have one of code.
          fontSize: 14.0, // text size
          scrollDuration: Duration(seconds: 1), // every scroll duration
          stopDuration: Duration(seconds: 3), //every stop duration
          tapToNext: false, // tap to next
          textColor: Colors.black, // text color
          controller: controller, // the controller can get the position
        ),
      ),
      onTap: () {
        print(controller.position); // get the position
      },
    );
  }
```