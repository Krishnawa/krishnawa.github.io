---
title: Smartphone Mirror Lens Mod; How I Did It
date: 2025-02-010 19:05:00 +530
categories: [Photography,Lens]
tags: [mirrorlens,camera, photography, mod]
comments: true
mermaid: true
math: true
image:
    path: https://i.postimg.cc/sfNbwMyT/cam-title.png
    lqip: https://i.postimg.cc/sfNbwMyT/cam-title.png
    alt: SHARP Aqous R6 back panel opened
---

## Story  

I have a [SHARP Aquos R6](https://jp.sharp/products/aquos-r6/) as a secondary backup smartphone in case of emergencies. I bought it very cheaply from a refurbished online store, it was a great deal for me, and the specs were also really good!  

On December 20, 2024, I was riding my bike to my friend's home. While on the way, I used this phone for navigation. Unfortunately, I met with an accident. I was riding peacefully at a speed of 45-50 km/h when suddenly a Swiggy delivery boy blindly overtook a vehicle very close to me. We collided, and it was a terrible situation.  

Luckily, I was wearing my riding gear, as I always do, which protected me from physical injuries. However, my bike and phone weren’t as fortunate—both were severely damaged. 😢  

After the accident, we went to the hospital for a check-up. A couple of months later, once everything was back to normal, I inspected my broken phone. Fortunately, there were no issues with its functionality. It only had minor scratches on the edges, but the back glass panel was shattered into a million pieces. 😢  
![Broken phone](https://i.postimg.cc/k56Q80k4/Broken.png){: lqip="https://i.postimg.cc/k56Q80k4/Broken.png" }
_Broken phone_


## Inspiration

So, I'm very obsessed with smartphone photography. I got a couple of **telephoto lenses, macro lenses, and wide-angle lenses**.  

I also tried to make a **DoF adapter** for my phone **three years ago**, but it didn't go well. I bought all the required components for a **Canon EF mount lens**, but except for the lens, I mistakenly bought a **Canon EF-M mount lens** instead. At that time, I thought both were the same.  

Anyway, I stuck with the project. There were so many challenges, but eventually, I gave up. You know, I tend to procrastinate, and over time, I completely forgot about this project.  

Recently, I saw some videos about the **Xiaomi 12S Ultra Concept**:  

<iframe width="800" height="450" src="https://www.youtube.com/embed/rZm4gg5CvWc" 
frameborder="0" allowfullscreen></iframe>  

I always wondered when something like this would be available in the market at an affordable price. But now, I think it's time to make one myself at a very low cost.

**So in this project I'm using a Canon 50mm EF-M mount lens for my phone sensor!**

Also, this YouTuber **[ModAndShoot](https://www.youtube.com/@ModAndShoot)** inspired me to take action. I really appreciate his work and want to thank him! 🚀  





## Specification
### Sharp Aquos R6 Camera Specifications  

| **Feature**               | **Specification**                                                                 |
|---------------------------|-----------------------------------------------------------------------------------|
| **Main Camera**           | **1-inch (1") Leica sensor**                                                     |
| **Resolution**            | **20 MP** (5,472 × 3,648 pixels)                                                 |
| **Sensor Size**           | **1-inch (13.2mm × 8.8mm)**                                                      |
| **Aperture**              | **f/1.9** (Wide)                                                                 |
| **Focal Length**          | **6.8mm (actual)** / **19mm (35mm equivalent)**                                  |
| **Lens**                  | **Leica Summicron 7-element lens**                                               |
| **Image Stabilization**   | **Electronic (EIS), No OIS**                                                     |
| **Autofocus**             | **Laser AF + PDAF**                                                              |
| **Flash**                 | **LED Flash**                                                                    |
| **Video Recording**       | **8K @ 30fps, 4K @ 120fps, 1080p @ 240fps**                                      |
| **Front Camera**          | **12.6 MP, f/2.3 aperture**                                                      |
| **Additional Features**   | **HDR10+, RAW support, Night mode**                                              |

---

#### **Key Highlights**  
- 📏 **Massive 1-inch sensor**: One of the largest smartphone sensors for exceptional low-light performance and dynamic range.  
- 🔴 **Leica-engineered lens**: Delivers superior clarity, color accuracy, and professional-grade imaging.  
- ❌ **No Optical Image Stabilization (OIS)**: Relies on **Electronic Image Stabilization (EIS)** for video and photo stabilization.  
- 🎥 **8K video recording**: Capture ultra-high-resolution videos at 30fps, with high-speed options like 4K @ 120fps and 1080p @ 240fps.  
- 🌍 **Ultra-wide 19mm focal length (35mm equivalent)**: Perfect for landscapes, street photography, and capturing more in the frame.  
- 🌙 **Night mode**: Enhanced low-light photography for stunning night shots.  
- 🎨 **RAW support**: Allows for professional post-processing and editing flexibility.  
- 💡 **HDR10+**: Ensures vibrant colors and high contrast in photos and videos.  

---


### TTArtisan 50mm f/1.2 Lens (Canon EF-M Mount) - Specifications

| **Specification**       | **Details**                                                                 |
|--------------------------|-----------------------------------------------------------------------------|
| **Focal Length**         | 50mm                                                                       |
| **Aperture Range**       | f/1.2 - f/16                                                               |
| **Lens Mount**           | Canon EF-M                                                                 |
| **Format Compatibility** | APS-C                                                                      |
| **Angle of View**        | Approximately 31.7° (on APS-C sensors)                                     |
| **Optical Construction** | 6 elements in 5 groups                                                     |
| **Aperture Blades**      | 10 (for smoother bokeh)                                                    |
| **Minimum Focus Distance**| 0.5m (50cm)                                                               |
| **Filter Thread Size**   | 52mm                                                                       |
| **Manual Focus**         | Yes                                                                        |
| **Autofocus**            | No                                                                         |
| **Image Stabilization**  | No                                                                         |
| **Dimensions**           | Approximately 56mm (diameter) x 55mm (length)                              |
| **Weight**               | Approximately 300g                                                         |
| **Build Material**       | Metal construction                                                         |
| **Coating**              | Multi-layer coating to reduce flare and ghosting                           |
| **Compatibility**        | Designed for Canon EF-M mount cameras (e.g., EOS M series)                 |

---

## Technical part you must know!

### About Actual Focal Length:
![Screenshot from PhotoPills](https://i.postimg.cc/502bFjW8/Screenshot-20250211-183827.png){: lqip="https://i.postimg.cc/502bFjW8/Screenshot-20250211-183827.png" }
_Screenshot from PhotoPills_
- The **actual focal length** of the **Sharp Aquos R6** is **6.8 mm**, which refers to the **physical distance** between the lens and the sensor when focused at infinity.
- **Actual focal length** is important for determining the **field of view**. A **6.8 mm lens** captures a **wider scene** compared to longer focal lengths.
- In smartphones with **smaller sensors**, the **field of view** may seem similar to that of a **longer lens** on a **full-frame** camera, which is why the **19mm (35mm equivalent)** is often mentioned.
- While **6.8 mm** is the **real focal length**, the **equivalent focal length** on a larger sensor is **19mm**, providing an idea of how the lens compares to those on traditional cameras.


### Flange Distance Explained
![FFD](https://i.postimg.cc/qvW13Ffw/Flange-back-back-focal-distance-1014x487.jpg){: lqip="https://i.postimg.cc/qvW13Ffw/Flange-back-back-focal-distance-1014x487.jpg"}
_FFD Representation_

The **flange focal distance (FFD)**, also called **flange-to-film distance**, is the distance between the **mounting flange** of the camera lens mount and the **image sensor plane**. It's a crucial measurement to ensure lenses focus correctly on the camera's sensor.

#### Why Flange Distance Matters:
1. **Lens Compatibility** – The **FFD** determines if a lens can be adapted to a camera body.  
   - Lenses with **longer FFDs** can be adapted to cameras with **shorter FFDs** using simple mechanical adapters.
  
2. **Precision** – Even small errors in the **FFD** can cause significant focus issues, which is why cameras are carefully calibrated to ensure accurate FFD.

3. **Film vs. Digital** –  
   - In **film cameras**, the **FFD** is measured to the **film plane**.
   - In **digital cameras**, it’s measured to the **image sensor plane**.
   - This difference is key when adapting lenses across systems.


### Flange Distance Table  

A comparison of popular camera systems and their flange distances.  

---

| **Camera System**                | **Flange Distance** | **Type**         | **Format**               |
|----------------------------------|---------------------|------------------|--------------------------|
| **Canon EF (Full-frame)**        | 44mm                | DSLR             | Full-frame               |
| **Canon EF-M (Mirrorless)**      | 18mm                | Mirrorless       | APS-C                    |
| **Nikon F (Full-frame)**         | 46.5mm              | DSLR             | Full-frame               |
| **Micro Four Thirds (MFT)**      | 19.25mm             | Mirrorless       | Micro Four Thirds        |
| **Sony E (Mirrorless)**          | 18mm                | Mirrorless       | APS-C / Full-frame       |
| **Leica M (Rangefinder)**        | 27.8mm              | Rangefinder      | Full-frame               |
| **Pentax K**                     | 45.46mm             | DSLR             | APS-C / Full-frame       |
| **Fujifilm X**                   | 17.7mm              | Mirrorless       | APS-C                    |
| **L-mount (Leica SL, Panasonic, Sigma)** | 20mm       | Mirrorless       | Full-frame               |
| **C-mount**                      | 17.526mm            | CCTV             | Small sensor             |

---



> More about flange focal distance is here [Wiki](https://en.wikipedia.org/wiki/Flange_focal_distance) and [THORLABS](https://www.thorlabs.com/newgrouppage9.cfm?objectgroup_id=14066)
{: .prompt-info }


zoom factror

## Procedure

### Software I used
Cad Challenge
curvature formula
## Prototypes

## Sample

## Next version changes
