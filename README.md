# ADDING CONSTRAINTS ACCORDING DEVICE ORIENTATION
Explaining in a clear way how to create vary traits constraints based on device orientation

## Desired result
![infN5](https://user-images.githubusercontent.com/110424672/203600662-1fd1a5e5-bd2e-4abd-ab1e-401a40a4a82e.png)

## Solution
### Step 1: 
Create **Portrait** view the usual way, using proper constraints. For example I had this:

<img width="364" alt="mXdxa" src="https://user-images.githubusercontent.com/110424672/203600889-b41a0341-c0ae-4b37-92e1-82f0c3df481c.png">


### Step 2:
Click Orientation button at the bottom of the view to flip the view to **landscape**

<img width="40" alt="Cqfoz" src="https://user-images.githubusercontent.com/110424672/203601006-43f219d9-fedf-4e0e-9e12-a07256dde73c.png">


### Step 3:
Add a **variation** for all constraints that require to be different on horizontal view. 
For example in my example **"SmallerView.leading = Safe Area.leading"** is still fine (needs no variation), but **"SmallerView.trailing = Safe Area.trailing"** makes no sense in horizontal view, I need **"SmallerView.trailing = LargerView.leading"** instead. So I need to add variation to both, **"SmallerView.trailing = Safe Area.trailing"**, and **"LargerView.leading"**.

To do that, I simply open **Attributes Inspector** for a constraint I need to vary, find the word **_Installed_**, and click on _Add Variation_ (+ button) on the left of it:

<img width="245" alt="UWzgj" src="https://user-images.githubusercontent.com/110424672/203601120-8bd73c41-7da1-4ee4-878e-350a779b7c65.png">

The variation I want to add is for **Compact Height**, and either **Regular** or **Any Width** (depends on which devices you are planning to support). Click _Add Constraint_.

<img width="193" alt="DuYTy" src="https://user-images.githubusercontent.com/110424672/203601212-7021463b-a819-47cf-88cf-4f82a4cdae07.png">

Now I see this:

<img width="216" alt="E7lEo" src="https://user-images.githubusercontent.com/110424672/203601369-40cf324e-afdc-4b6c-b8e5-56a90ec24958.png">


But I want to use this constraint only in Portrait view, so I need to **uncheck hC**:

<img width="205" alt="I9O75" src="https://user-images.githubusercontent.com/110424672/203601404-b25695df-a24c-4d02-ba75-3e3285c9b528.png">

Do the same for all other constraints that won't work for Horizontal view.


### Step 4:

Now I need to add constraints specific to horizontal view. To do that, switch to horizontal view (the Orientation button at the toolbar at the bottom)

You will now see your constraints with some of them disabled:

<img width="379" alt="FE82n" src="https://user-images.githubusercontent.com/110424672/203601582-b0e0e377-e702-459c-92b8-e26f312cb13e.png">

And now you can add missing constraints. For example in my case I added 3 new constraints:

<img width="327" alt="RR890" src="https://user-images.githubusercontent.com/110424672/203601640-4869b1cc-cef9-441e-9d31-bac8efe4b583.png">


### Step 5:

Switch to Portrait, and now disable those additional constraints from step 4 in portrait mode. This time you **uncheck Installed that has no hC prefix**:

<img width="211" alt="0cfHs" src="https://user-images.githubusercontent.com/110424672/203601817-d522d775-272f-4f3c-bb65-caf0f482aae3.png">

**Logos Backup**


![Logo-at-top_-name-at-bottom](https://github.com/user-attachments/assets/e2d54d73-ab96-4d00-a2d6-a47287cc8c5e)

![Logo-at-left_-name-at-right](https://github.com/user-attachments/assets/cb35752c-e317-484a-84a6-1c5ab1a6a684)

![Just-Logo](https://github.com/user-attachments/assets/e9b467c4-a619-46cf-a77d-3e8aae76a3a3)

![Logo-at-left_-name-at-right30Percenmt](https://github.com/user-attachments/assets/368cfacc-14cc-4491-ba67-0e4aadbc0e66)
