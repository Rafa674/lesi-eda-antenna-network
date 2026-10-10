# Antenna Grid and Graph

A console-based C project for managing antennas on a 10 × 10 grid. It supports antenna placement and removal, calculates harmful-effect locations for antennas with matching frequencies, and provides a graph model with automatic connections and traversal algorithms.

## Features

- Add, remove, and display antennas on a 10 × 10 grid.
- Validate grid coordinates and prevent multiple antennas from occupying the same position.
- Calculate and display harmful-effect positions (`#`) for antennas with the same frequency.
- Represent antennas as graph vertices and connect vertices that share a frequency.
- Display the graph and its vertices and adjacency lists.
- Traverse the graph using depth-first search (DFS) and breadth-first search (BFS).
- Load and save antenna and graph data in text and binary files.

## Requirements

- Windows and Microsoft Visual Studio 2022 with the C++ desktop development workload.
- The project uses the Visual Studio v143 toolset and includes `trabalho eda.vcxproj`.

## Build and run

1. Open `trabalho eda.vcxproj` in Visual Studio.
2. Select the **Debug | Win32** configuration.
3. Build the project and run the generated console application.

The application reads and writes its data files in the current working directory. Ensure that directory is writable. The Win32 configuration avoids the machine-specific external library paths currently present in the x64 project configurations.

## Using the application

The main menu contains separate menus for antennas and the graph. Enter the number of the desired option when prompted.

### Antennas

- Enter a frequency character and X/Y coordinates to add an antenna.
- Enter the antenna's frequency and coordinates to remove it.
- Choose the list option to display the grid. Antennas appear as their frequency character, empty cells as `.`, and calculated harmful-effect positions as `#`.
- Valid coordinates range from `0` to `9` on both axes.

### Graph

- Add a vertex by entering its frequency and X/Y coordinates. Vertices with matching frequencies are connected automatically.
- Remove vertices by ID, display the grid or vertex adjacency lists, and run DFS or BFS from a vertex ID.

## Data files

The application looks for these files in its working directory:

| Data | Binary file | Text file |
| --- | --- | --- |
| Antennas | `antenas.bin` | `antenas.txt` |
| Graph | `grafo.bin` | `grafo.txt` |

When starting, it attempts to load the binary file first and falls back to the text file if the binary file cannot be opened. The text grid uses `.` for an empty cell and a frequency character for an occupied cell. Changes made through the menus are written to the corresponding data files.

## Project files

- `main.c` — console menus and application flow.
- `funcoes.c` — antenna, harmful-effect, graph, persistence, DFS, and BFS operations.
- `funcoes.h` — function declarations.
- `dados.h` — data structure definitions.
