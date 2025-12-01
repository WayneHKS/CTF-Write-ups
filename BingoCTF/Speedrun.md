# BingoCTF - Speedrun Write-up  
**Challenge Creator:** @Cofastic  

> “I was at an incredible pace during my Minecraft RSG Any% speedrun. But amidst the excitement, I completely blanked on the stronghold coordinates I found. I know I uploaded the footage somewhere online under my handle @Cofastic, but I can't remember which platform I used. The run was so good, I made sure to preserve it somewhere safe where it won't disappear forever. Can you help me track down those coordinates?”

**Flag Format:** `BINGOCTF{coordinateX_coordinateZ}`

---

## Recon

Based on the challenge description, we are looking for **footage** containing the coordinates of the Minecraft stronghold uploaded by `@Cofastic`.

Since this is essentially a simple OSINT/search task for a video uploaded online, I started by checking common video platforms:

- YouTube  
- Twitch  
- Other video hosting platforms

While going through these, I eventually found **two Minecraft videos** uploaded by **Cofastic** on the **Internet Archive**.

![Screenshot of Internet Archive search result for Cofastic’s Minecraft videos](image_of_internet_archives.png)

---

## Extracting the Coordinates

Inside these two videos, the player throws an **Eye of Ender** at two different locations. From the in-game debug screen (F3), we can obtain the coordinates and yaw:

- **Location 1:**
  - `X = 0.435`
  - `Z = 0.773`
  - `Yaw = -112.2°`

- **Location 2:**
  - `X = 350.362`
  - `Z = -0.261`
  - `Yaw = -116.6°`

---

## Calculating the Stronghold Position

Using these two sets of coordinates and yaw angles, we can plug them into an online **stronghold calculator** (commonly used by Minecraft speedrunners).  

By inputting:

- Point 1: `(0.435, 0.773)` with yaw `-112.2°`  
- Point 2: `(350.362, -0.261)` with yaw `-116.6°`  

The calculator returns the **exact stronghold location**:

- **Final Stronghold Coordinates:** `(1880, -766)`

---

## Flag

Following the flag format `BINGOCTF{coordinateX_coordinateZ}`, we get:

```text
BINGOCTF{1880_-766}
