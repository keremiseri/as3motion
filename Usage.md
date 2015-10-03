```

package com.hvilela {
import flash.display.*;
import com.hvilela.*;

public class MotionDetection extends Sprite {

private var controller:CameraController;

public function MotionDetection() {
controller = new CameraController(stage, stage.stageWidth, stage.stageHeight, stage.stageWidth / 8, stage.stageHeight / 8);
// The move map is locked by default for optimization reasons
controller.getMoveMap().unlock();

// Add the actual scene (webcam) to the scene
var actual:Bitmap = new Bitmap(controller.getActual());
addChildAt(actual, 0);

// Add the move map (white boxes) to the scene
var moveMap:Bitmap = new Bitmap(controller.getMoveMap());
moveMap.width = actual.width;
moveMap.height = actual.height;
moveMap.blendMode = BlendMode.SCREEN;
addChild(moveMap);
}
}
}
```