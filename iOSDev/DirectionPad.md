手柄的八方向键按键判定示例逻辑。

```swift
override func touchesBegan(_ touches: Set<UITouch>, with event: UIEvent?) {
    super.touchesBegan(touches, with: event)
    let directionCenterPoint: CGPoint = directionCenter.center
    let directionMaxRadius: CGFloat = CGRectGetHeight(inputPanel.frame) * 0.3
    for touch in touches {
        let touchPoint = touch.location(in: inputPanel)
        let dis = touchPoint.distance(to: directionCenterPoint)
        if dis < directionMaxRadius {
            let deltaX = touchPoint.x - directionCenterPoint.x
            let deltaY = touchPoint.y - directionCenterPoint.y
            let angle = atan2(deltaY, deltaX) * 180.0 / .pi
            let normalizedAngle = angle < 0 ? angle + 360 : angle
            
            var detectedDirection: Direction = .Right
            
            for (direction, startAngle, endAngle) in directions {
                if normalizedAngle >= startAngle && normalizedAngle < endAngle {
                    detectedDirection = direction
                    break
                }
            }
            
            if normalizedAngle >= 330.0 && normalizedAngle <= 360.0 {
                detectedDirection = .Right
            }
            
            NSLog("\(detectedDirection)")
        }
    }
}

private let directions: [(Direction, Double, Double)] = [
    (.Right, 0.0, 30.0),
    (.RightDown, 30.0, 60.0),
    (.Down, 60.0, 120.0),
    (.LeftDown, 120.0, 150.0),
    (.Left, 150.0, 210.0),
    (.LeftUp, 210.0, 240.0),
    (.Up, 240.0, 300.0),
    (.RightUp, 300.0, 360.0)
]

enum Direction {
    case Left, Right, Up, Down, LeftUp, LeftDown, RightUp, RightDown
}
```
