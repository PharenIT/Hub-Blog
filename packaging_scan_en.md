# Case Study: Automated Packaging Scanning with Rust

![Industrial packaging and barcode scanner](package_scanner.jpg)

## Introduction

On the factory floor, every second counts. Each moment determines how many packages can be shipped and whether the right boxes are used. We were asked to build a system that makes choosing the right carton as easy as a gesture: place the package, and in less than half a second the outline is captured, the measurements are calculated and the appropriate label is printed.

## Client & Key Facts

| Client | Platform type | Team | Industry | Users | Location | Market | Project duration |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Industrial company | Desktop-/Mobile app | PM, Rust dev, computer vision, UI/UX, QA | Manufacturing | Production staff, logistics teams | Europe | worldwide | 3 months |

## Business Value

During our tour of the plant we saw many employees measuring boxes by hand, jotting numbers on scraps of paper and often selecting boxes that were too large. This wastes material, leads to higher shipping costs and takes time. Modern 3D sensors can accurately scan irregularly shaped packages; they capture dimensions such as volume, height, width and length and help to optimise storage and transport space【375008585752810†L1101-L1106】. They also detect defects and misalignments that aren’t visible to traditional 2D cameras【375008585752810†L1108-L1115】.

- **Speed:** The process takes less than 0.5 seconds – far quicker than manual measuring.
- **Quality:** 3D sensors detect dents or tears【375008585752810†L1108-L1115】.
- **Cost savings:** Accurate measurements reduce packaging material and shipping volume, noticeably lowering costs.
- **Data transparency:** Every scan is stored and can be used for analysis.

## User Experience

The application is designed to work even in industrial environments. Buttons that can be pressed with gloves, clear colours and large type ensure you understand the process at a glance. The system guides users through each step: scan the contour, display the measurements, suggest a box size and print the label. The same software runs on tablets for mobile use, for example at goods receiving.

## Customer Benefits

- **Lightning-fast scanning:** The outline is captured in less than 0.5 seconds.
- **Error-free measurements:** Automation eliminates incorrect values and makes handwritten notes obsolete.
- **More packages per shift:** Teams can significantly increase their productivity.
- **Data for quality control:** Historical scan values help to optimise processes and identify trends.
- **Easy scaling:** Thanks to the cross‑platform architecture, the app runs on various devices.

## Business Impact

The automated solution has revolutionised the packaging process: incorrectly sized shipments have become the exception, shipping costs are falling and returns are decreasing. Employees appreciate the relief and can use their time more effectively. Data is transferred directly to the ERP and is available for controlling.

## Project Requirements

The customer wanted a fast, reliable system that can recognise boxes of different sizes and shapes, automatically select the right class and create labels. The app had to work offline, connect easily to the ERP and be usable both at a stationary workstation and on mobile devices.

### Project Phases

#### Discovery (1 week)

We spent a few days in the plant, observing the packaging process and talking to staff. Together we identified bottlenecks and gathered requirements. A 3D scanner seemed ideal because it reliably captures irregular shapes【375008585752810†L1101-L1106】.

#### UI/UX Design (2 weeks)

We then developed wireframes and interactive prototypes. In feedback sessions we tested the concepts directly with users. Adjustments such as larger buttons or colour coding came out of these conversations.

#### Development & Integration (5 weeks)

The software was written in Rust. We used **Tauri** and **Crux** for the cross‑platform UI; Tauri produces lightweight, performant apps【477875218039410†L46-L63】, and Crux separates core logic from the UI【932251511387094†L134-L138】【932251511387094†L192-L220】. We also integrated:

- An **OpenCV** binding for image and 3D data processing.
- **Sensor adapters** to read data from the scanner.
- **Classification logic** for box sizes.
- **Label printer interface**.
- **Local storage** for offline operation and later synchronisation.

## Our Solution & Architecture

At the heart of our application is a Rust service that receives sensor data, processes it and returns results. The UI layer accesses it via an internal API. Events such as "scan started" or "label printed" are passed through an event dispatcher. When there is no network connection, data is stored locally and synchronised later.

## Highlights & Design

- **Sub‑second per scan:** Each process completes in under 0.5 seconds.
- **Quality control included:** Dents and tears are detected【375008585752810†L1108-L1115】.
- **Automatic size selection:** The appropriate box size is suggested.
- **Label creation:** Integrated printing with barcode.
- **Offline functions:** Save and synchronise later with the ERP.
- **Dashboard:** Analyse throughput times and errors.

## Outcome

Thanks to the solution, teams work faster and make fewer errors. Packaging material is used more efficiently and shipping costs decrease. Customer reports show fewer damages and faster delivery. The app is now used at several sites, and the investment has paid off quickly.

## Conclusion

Technology alone doesn’t solve problems – understanding people’s day‑to‑day work does. Our project proves that by listening to users and tailoring the solution to their workflows, modern software can achieve a great deal.
