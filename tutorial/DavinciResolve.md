# Davinci Resolve Tutorial

<details>
      <summary>Install Davinci Resolve on Arch Linux</summary>
      
1. Download the software from the [website](https://www.blackmagicdesign.com/products/davinciresolve)
2. Install prerequisites
      pacman -S fuse
3. Unzip the downloaded file
4. Make it executable
      chmod +x ./davinci_resolve_installer.run
5. Start the installation
      sudo ./davinci_resolve_installer.run -i
</details>

<details>
      <summary>Add a Frame with Solid Color</summary>
<br>
Select Effects > Generators > Solid Color
   <br>
   <br>
   <img width="640" height="220" alt="image" src="https://github.com/user-attachments/assets/c5694c91-56bb-45be-8da6-4d8be362bff6" />

   
7. Drag "Solid Color" to your Timeline ( Video Track 01 - V1 )
8. Right Click the Solid Color Clip on the Timeline
9. Select "Clip Color" ( Or "Inspector" in the Top Right Corner )
</details>




## Import an Image to the Frame
1. Click "Media Pool" ( Top Left Corner )
2. Press Ctrl+I and select the Image
3. Drag your Imported Image to the Timeline ( Video Track 2 - V2 )
4. Resize the Image under Inspector ( Top Right Corner ) > Transform > Zoom

## Move an Image on a Trajectory
### 1. Set the Starting Point
- Move your timeline playhead (the red vertical line) to where you want the movement to start
- In the Inspector > Transform section, find Position
- Click the small Diamond Icon (Keyframe button)
### 2. Create the Trajectory
- Move the playhead forward in the timeline (e.g., move it 2 seconds forward).
- Now, change the Position X and Position Y values in the Inspector to move the image to a new spot. 
(Alternatively, you can click the rectangular "Transform" icon just below the video viewer to drag the image manually on screen).
- Note: A new keyframe is automatically created as soon as you move the image.
### 3. Add Curves or Corners (Specific Trajectory)
- To make a complex path (not just a straight line), move the playhead forward again, and move the image to a third position.
- Repeat this for as many turns or curves as you need.
### 4. Visualize the Path
- To see the actual line (trajectory) the image will follow, make sure the Transform On-Screen Control is active 
(click the box icon in the bottom-left corner of the video viewer). You will see a dotted line representing your animation path.
