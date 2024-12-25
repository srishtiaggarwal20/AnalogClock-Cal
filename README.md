# Psdude - A Digital and Analog Clock

## Overview

Psdude is a Java-based application that displays both a digital clock and an analog clock with a calendar layout. The application showcases real-time updating of the current time and date, and presents a graphical user interface (GUI) with components such as a calendar, clock hands, and labels. It uses the `javax.swing` and `java.awt` libraries for GUI rendering, with date and time management handled using the `java.util.Calendar` class and `java.text.SimpleDateFormat`.

## Features

- **Digital Clock Display**: Shows the current time in hours, minutes, and seconds.
- **Analog Clock Display**: Shows an analog clock with hour, minute, and second hands that rotate in real-time.
- **Calendar**: Displays the current year, month, and day in a structured layout.
- **Custom Labels**: The clock has custom labels and text that identify the application and its creator.
- **Interactive Components**: The digital clock and calendar have distinct visual representations with buttons for possible interactions.

## Technologies Used

- **Java 1.8+**
- **Java Swing**: For building the graphical user interface (GUI).
- **Java AWT**: For graphics rendering.
- **SimpleDateFormat**: For formatting date/time information.
- **GregorianCalendar**: For handling calendar operations.

## Dependencies

No external dependencies. This application uses standard Java libraries.

## How It Works

### GUI Setup:
- The clock is centered on the screen and displayed within a `JPanel` object. The window is created using `JFrame`, and the custom `Psdude` panel is added to the content pane.
- The calendar layout consists of rounded rectangles for labels and buttons, along with text displaying the current date (DD, MM, YYYY) and time (HH, MM, SS).

### Digital Clock:
- The digital clock displays the time in hours, minutes, and seconds. The `SimpleDateFormat` is used to extract the current second, minute, and hour from the system time.

### Analog Clock:
- The analog clock is drawn with hour, minute, and second hands using graphics primitives (lines and ovals). The positions of these hands are calculated based on the current time, and the hands are updated every second to reflect the passage of time.

### Threading:
- A separate thread (`Thread`) is used to update the clock every second. The `run()` method of the thread calls `repaint()` to refresh the display, ensuring that the time and calendar values are updated every second.

## Code Structure

### 1. Psdude Class
- **Attributes**:
  - `Thread thread`: The clock thread used to update the display at regular intervals.
  - `Variables (i, j, k, p, q)`: Represent the current second, minute, hour, and coordinates for the clock hands.
  - `String year, month, day, second, minute, hour`: These hold the current date and time.
  - `SimpleDateFormat sdf`: A formatter to extract date and time components.
  - Coordinates (`xOrigin, yOrigin, xsec, ysec, xmin, ymin, xhr, yhr`): Coordinates for clock components.

- **Methods**:
  - `clockLayout(Graphics g)`: Draws the calendar, digital clock, and layout.
  - `paint(Graphics g)`: The method responsible for rendering the clock and updating the hands' positions.
  - `startclock()`: Starts the clock thread.
  - `run()`: Continuously updates the time by repainting the frame every second.

### 2. Main Method
- The main method initializes the frame (`JFrame`), sets the background color, and adds the `Psdude` panel to the content pane.
- Calls `ps.startclock()` to initiate the clock updating mechanism.

## Installation

To run this project:

1. Clone or download the repository to your local machine.
2. Compile the Java code:
    ```bash
    javac Psdude.java
    ```
3. Run the compiled class:
    ```bash
    java Psdude
    ```
4. You should see a window with a graphical digital and analog clock along with the calendar displayed.






