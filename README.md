# TensorFlow Examples

<div align="center">
  <img src="https://www.tensorflow.org/images/tf_logo_social.png" /><br /><br />
</div>

<h2>Most important links!</h2>

* [Community examples](./community)
* [Course materials](./courses/udacity_deep_learning) for the [Deep Learning](https://www.udacity.com/course/deep-learning--ud730) class on Udacity

If you are looking to learn TensorFlow, don't miss the
[core TensorFlow documentation](http://github.com/tensorflow/docs)
which is largely runnable code.
Those notebooks can be opened in Colab from
[tensorflow.org](https://tensorflow.org).

<h2>What is this repo?</h2>

This is the TensorFlow example repo.  It has several classes of material:

* Showcase examples and documentation for our fantastic [TensorFlow Community](https://tensorflow.org/community)
* Provide examples mentioned on TensorFlow.org
* Publish material supporting official TensorFlow courses
* Publish supporting material for the [TensorFlow Blog](https://blog.tensorflow.org) and [TensorFlow YouTube Channel](https://youtube.com/tensorflow)

We welcome community contributions, see [CONTRIBUTING.md](CONTRIBUTING.md) and, for style help,
[Writing TensorFlow documentation](https://www.tensorflow.org/community/contribute/docs_style)
guide.

To file an issue, use the tracker in the
[tensorflow/tensorflow](https://github.com/tensorflow/tensorflow/issues/new?template=20-documentation-issue.md) repo.

## License

[Apache License 2.0](LICENSE)


# Image Segmentation Android sample.

The used model, DeepLab
[https://ai.googleblog.com/2018/03/semantic-image-segmentation-with.html] is a
state-of-art deep learning model for semantic image segmentation, where the goal
is to assign semantic labels (e.g. person, dog, cat) to every pixel in the input
image.

## Requirements

*   Android Studio 3.2 (installed on a Linux, Mac or Windows machine)
*   An Android device, or an Android Emulator

## Build and run

### Step 1. Clone the TensorFlow examples source code

Clone the TensorFlow examples GitHub repository to your computer to get the demo
application.

```
git clone git@github.com:spoorgholi74/tflite_example.git
```

### Step 2. Import the sample app to Android Studio

Open the TensorFlow source code in Android Studio. To do this, open Android
Studio and select `Import Projects (Gradle, Eclipse ADT, etc.)`, setting the
folder to `examples/lite/examples/image_segmentation/android`

### Step 3. Run the Android app

Connect the Android device to the computer and be sure to approve any ADB
permission prompts that appear on your phone. Select `Run -> Run app.` Select
the deployment target in the connected devices to the device on which the app
will be installed. This will install the app on the device.

#### Switch between inference solutions (Task library vs TFLite Interpreter)

This image segmentation Android reference app demonstrates two implementation
solutions:

(1)
[`lib_task_api`](https://github.com/tensorflow/examples/tree/master/lite/examples/image_segmentation/android/lib_task_api)
that leverages the out-of-box API from the
[TensorFlow Lite Task Library](https://www.tensorflow.org/lite/inference_with_metadata/task_library/image_segmenter);

(2)
[`lib_interpreter`](https://github.com/tensorflow/examples/tree/master/lite/examples/image_segmentation/android/lib_interpreter)
that creates the custom inference pipleline using the
[TensorFlow Lite Interpreter Java API](https://www.tensorflow.org/lite/guide/inference#load_and_run_a_model_in_java).

The [`build.gradle`](app/build.gradle) inside `app` folder shows how to change
`flavorDimensions "tfliteInference"` to switch between the two solutions.

Inside **Android Studio**, you can change the build variant to whichever one you
want to build and run — just go to `Build > Select Build Variant` and select one
from the drop-down menu. See
[configure product flavors in Android Studio](https://developer.android.com/studio/build/build-variants#product-flavors)
for more details.

To test the app, open the app called `TFL Image Segmentation` on your device.
Re-installing the app may require you to uninstall the previous installations.

For gradle CLI, running `./gradlew build` can create APKs for both solutions
under `app/build/outputs/apk`.

*Note: If you simply want the out-of-box API to run the app, we recommend
`lib_task_api` for inference. If you want to customize your own models and
control the detail of inputs and outputs, it might be easier to adapt your model
inputs and outputs by using `lib_interpreter`.*

## Resources used:

*   Camera2:
    https://developer.android.com/reference/android/hardware/camera2/package-summary
*   Camera2 base sample:
    https://github.com/android/camera-samples/tree/master/Camera2Formats
*   TensorFlow Lite: https://www.tensorflow.org/lite
*   ImageSegmentation model:
    https://www.tensorflow.org/lite/models/segmentation/overview

