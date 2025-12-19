# Image Targets

<figure><img src="../../.gitbook/assets/mars_4_astronaut.jpg" alt=""><figcaption></figcaption></figure>

An Image Target allows Vuforia to detect and track a flat image in the real environment. This makes it possible to anchor virtual content relative to the position of that image, as shown in the figure below:

{% embed url="https://developer.vuforia.com/library/vuforia-engine/images-and-objects/image-targets/image-targets/" %}

***

### Using the sample dataset

In the scene with the **ARCamera**, create an **Image Target**–type GameObject (from the top menu _GameObject_, or by right-clicking in the _Hierarchy_ view):

<figure><img src="../../.gitbook/assets/empty_target.png" alt=""><figcaption><p>Image Target without an image to track</p></figcaption></figure>

If in the `ImageTargetBehavior` component we change the type to ‘From Database’, Vuforia will offer us the option to **install a set of default images**, those from the ‘VuforiaMars\_Images’ database:

<div><figure><img src="../../.gitbook/assets/import_default_dataset.png" alt="" width="372"><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/image_target_props.png" alt=""><figcaption></figcaption></figure></div>

Depending on the Image Target we choose, we will be able to track one image or another:

<figure><img src="../../.gitbook/assets/four_targets.png" alt=""><figcaption><p>Images from the default dataset</p></figcaption></figure>

To anchor synthetic content so that it appears in AR, we must add those GameObjects as **children of the target**:

<figure><img src="../../.gitbook/assets/content.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
The component responsible for showing and hiding the synthetic content is the `DefaultObserverEventHandler`.

This component enables/disables, for the target’s children:

* Renderer
* Collider
* Canvas (UI)

If you want to enable/disable other elements you can either:

* Use the events from the editor (recommended), or
* Create your own script that inherits from DefaultObserverEventHandler (more complex).

<img src="../../.gitbook/assets/default_observer_event_handler.png" alt="" data-size="original">
{% endhint %}

<figure><img src="../../.gitbook/assets/track_astronaut.gif" alt="" width="563"><figcaption></figcaption></figure>

### Creating an image dataset

To create a **custom dataset**, we need to go to the _Vuforia's Target Manager_:

{% embed url="https://developer.vuforia.com/develop/databases" %}

We can add, for instance, these two images:

<div><figure><img src="../../.gitbook/assets/sinchan_target.jpg" alt="" width="170"><figcaption></figcaption></figure> <figure><img src="../../.gitbook/assets/doraemon_target.jpeg" alt="" width="375"><figcaption></figcaption></figure></div>

From the _Target Manager_, we have to **generate a Database**:

<figure><img src="../../.gitbook/assets/create_database.png" alt="" width="563"><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/generate_popup.png" alt="" width="563"><figcaption></figcaption></figure>

After generating the Device Database, we can **add the two images**:

<figure><img src="../../.gitbook/assets/adding_the_target.png" alt="" width="375"><figcaption></figcaption></figure>

{% hint style="warning" %}
It is important to add the width of the real target (in meters) so that the scale is correctly rendered in Unity (1 unit ⇒ 1 meter), though we can set 1 by default.
{% endhint %}

After adding the two images, we can observe the set of images that belong to the database:

<figure><img src="../../.gitbook/assets/list_of_targets.png" alt=""><figcaption></figcaption></figure>

If we select a target, we can preview the "**feature points**". The more feature points it has, the better Vuforia will perform in recognizing and tracking it:

<figure><img src="../../.gitbook/assets/target_features.png" alt=""><figcaption></figcaption></figure>

The next step is to download the database and import it into the Unity project (by double-clicking on the .unitypackage file):

<figure><img src="../../.gitbook/assets/Captura de pantalla 2025-12-02 a las 16.03.17.png" alt="" width="563"><figcaption></figcaption></figure>

After that, we will be able to select our database and use their images as targets:

<figure><img src="../../.gitbook/assets/doraemon_target_elements.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/two_target.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/dor_sin_example.gif" alt=""><figcaption></figcaption></figure>
