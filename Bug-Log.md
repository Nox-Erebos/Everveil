# Bug Log

# Bug Fix Log: [Player and World Collision Bug]

#### Date: 29-10-2026
#### Status: $\color{green}{\text{Fixed}}$
#### System: General Interaction with World

---

## The Problem
* **What went wrong:** The character, when sprinting against buildings from the asset Sci-fi Kit Vol 4, would be launched at high speeds sideways away from the sprinting position in the direction they were sprinting. This action, on some occasions, clipped the player through the terrain. The player was also shaking on the aforementioned GameObjects.

---

##  The Investigation

1. **The Test:** Tested sprinting with normal GameObjects with a normal basic Box Collider and Mesh Collider.
2. **The Discovery:** Realized the issue was due to the presence of the **Common Map** physics material.
3. **The Root Cause:** Opsive's Ultimate Character Controller Version 3.0.11 has its own custom movement script; when this script interacts with the aforementioned physics material, it causes the bounciness to increase. It starts with an acceleration followed by a launch.

---

## The Fix

1. **Edited Physics Materials:** Set the physics material for all GameObjects related to structures in Sci-fi Kit Vol4 to none in Prefab Mode.

---

## 💡 What I Learned

* When designing a world, I should strive to make the colliders of GameObjects as simple as possible.
