# godam

| Feature                      | Description                                                 |
| ---------------------------- | ----------------------------------------------------------- |
| 🔢 Phone Number Input        | Triggers the session; order is fetched (e.g. from DB).      |
| 📦 Order Display             | System knows person `X` needs to take 50 Wai Wai, etc.      |
| 🎥 Camera Feed               | Track cartons person carries as they exit (e.g. near door). |
| 📦 Carton Detection          | Detect **each carton**, even if stacked.                    |
| 🧍 Person Tracking           | Track each person’s movements — each carry/return.          |
| 🔄 Carton-Person Association | Match cartons carried with the right person.                |
| 🔁 Session Management        | Accumulate carried cartons over multiple trips.             |
| 🧾 Logging                   | Compare actual vs. expected and store per phone number.     |

| Task                            | Technology                               | Why?                                                  |
| ------------------------------- | ---------------------------------------- | ----------------------------------------------------- |
| **UI for Phone Entry**          | Flask + HTML/JS (or Tkinter)             | Easy to deploy touchscreen UI                         |
| **Camera Handling**             | OpenCV                                   | Interface with USB/IP cams                            |
| **Carton Detection**            | YOLOv8 (custom-trained)                  | Generic carton detection, regardless of brand         |
| **Person Detection & Tracking** | YOLOv8 + DeepSORT                        | Accurate tracking even in stacks or groups            |
| **Carton-Person Matching**      | Proximity-based logic + session tracking | Tie cartons to specific person by location and timing |
| **Session Management**          | Python logic + SQLite/MySQL              | Track how many cartons picked per person              |
| **Violation Detection**         | Custom rule-based logic                  | Compare expected vs. actual count                     |
| **Dashboard (Optional)**        | Flask + Chart.js                         | View who took how many, with over/under flags         |
