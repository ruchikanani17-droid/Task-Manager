# Task-Manager
## The Design Journey & Problem Solving

### Initial Concept vs. Final Design
Originally, I planned to style this as a chunky, nostalgic "Windows 95" retro task board. However, halfway through prototyping, I realized I wanted a UI that felt more modern, warm, and personal. 

**The Changes I Made:**
I completely pivoted the aesthetic to a "Chai & Neko" theme—blending warm Indian tones (cream and marigold) with Japanese Kawaii elements (sakura pink and cats). I stripped away the retro borders and implemented modern design. I also expanded the layout to include two distinct, dynamic tables: one for Active Tasks and one for a Completed History log.

### Challenges & Solutions

**Struggle 1: Complex Character Animations**
I wanted to include highly specific, cute character animations inside the app (e.g., a tired character yawning at the top, and a character leaning against the app fixing a sliding blanket). Initially, I struggled with how to code these complex movements using just CSS.
* **The Fix:** I shifted from a "coding" mindset to a "UI/UX" mindset. Instead of trying to draw and animate complex vectors with raw code, I mapped out spatial containers (`div` blocks) and sourced animated GIFs. By embedding these via `<img>` tags, I let the browser handle the heavy lifting of the animation while maintaining the seamless aesthetic of the app.

**Struggle 2: Messy Table Numbering (Data vs. UI)**
When users deleted a task or moved it to the "Completed" history, the serial numbers in the table would break, skip numbers, or expose the raw, messy backend array IDs. 
* **The Fix:** I completely decoupled the visual UI numbering from the backend data array. I engineered the JavaScript rendering function to dynamically calculate and generate sequential serial numbers (`index + 1`) purely on the front-end *during* the render phase. This guarantees that no matter how many tasks are added, deleted, or moved, the UI always presents a pristine, mathematically perfect ledger (1, 2, 3...) to the user.
