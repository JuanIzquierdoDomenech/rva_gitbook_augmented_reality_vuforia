---
icon: kaaba
---

# Area Targets

An Area Target in Vuforia is a special type of trackable that allows us to:

* Pre-scan an environment using a specialized device, such as an iPhone/iPad with LiDAR
* Export the scanned environment to Unity for development
* Detect the environment in AR

{% embed url="https://developer.vuforia.com/library/vuforia-engine/environments/area-targets/area-targets/" %}

#### <mark style="background-color:$info;">Note on Android users for scanning</mark>

**Scanning an environment** can only be done if you have an iPhone/iPad, since the app that scans the environment is only available for iOS devices:

{% embed url="https://apps.apple.com/us/app/vuforia-creator/id1625877749" %}

However, the developed app **can be developed** for both **Android** and **iOS** devices.

***

## Creating an Area Target with the Vuforia Creator app

* **Download** the _Vuforia Creator_ app on an iOS app
* Open the app and enter your Vuforia **credentials**
* Create a **new asset** of type "_Capture Area_" and save it

<div><figure><img src="../.gitbook/assets/scannin.gif" alt="" width="375"><figcaption></figcaption></figure> <figure><img src="../.gitbook/assets/vuforia-creator-app-capture-area- workflow-copy.png" alt=""><figcaption><p>Scanning workflow</p></figcaption></figure></div>

* **Long press** on the asset and **share it** with your computer

<figure><img src="../.gitbook/assets/share_asset.jpg" alt="" width="375"><figcaption></figcaption></figure>

* The exported file will be a .zip file. **Unzip** it, locate the _.unitypackage_ file and double-click on it while the Unity project (with the Vuforia SDK) is open to import it

<figure><img src="../.gitbook/assets/import_area.png" alt="" width="563"><figcaption></figcaption></figure>

***

## Scene setup

* Replace the **Main Camera** with the Vuforia's **AR Camera** (as usual), making sure the App License Key is setup
* Create a _Vuforia Engine → Area Target → Area Target_

{% hint style="info" %}
Since there is only one asset, your scanned map will appear automatically
{% endhint %}

<figure><img src="../.gitbook/assets/load_map.png" alt=""><figcaption></figcaption></figure>

* Add **children GameObjects**, since an Area Target behaves like the other targets we have seen so far. For this example, we will add some **cubes** and **spheres**, some of them with **rigidbodies**.

{% hint style="info" %}
Vuforia is capable of performing automatic occlusion and collision if needed.
{% endhint %}

<figure><img src="../.gitbook/assets/occlusion_collision_props.png" alt=""><figcaption></figcaption></figure>

* Test the app inside the Unity Editor by changing the **PlayMode Type** from WEBCAM to **SIMULATOR** in the Vuforia Configuration file

<div><figure><img src="../.gitbook/assets/change_to_simulatr.png" alt="" width="375"><figcaption></figcaption></figure> <figure><img src="../.gitbook/assets/test_in_editor.gif" alt="" width="375"><figcaption></figcaption></figure></div>

* Since the target might be found after the scene executes, elements affected by the **physics engine** will **fall into the void**. To avoid this, uncheck the "`Use Gravity`" property on the GameObjects with a `RigidBody` component
* Now, **when the target is found**, activate that property back

<figure><img src="../.gitbook/assets/Captura de pantalla 2025-12-09 a las 13.11.57.png" alt="" width="375"><figcaption></figcaption></figure>

### Result

<figure><img src="../.gitbook/assets/result_area.gif" alt=""><figcaption></figcaption></figure>
