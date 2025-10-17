# GreenPass-Tracker (C and Linked Lists)
This is the solution to my practical exam for the University of Ferrara (UNIFE) course "Programming and Laboratory", Academic Year 2022/2023. By handling **dynamic data structures** in **C Programming**, the goal was to process an unsorted list of medical events (tests/vaccines) and generate a summary of each person's immunity status, presented in a dynamically created and maintained **sorted linked list**.

## Key Concepts
- **Low-Level C Programming:** Entirely implemented in C, showcasing proficiency with manual memory management.
- **Pointers-to-Pointers (`**Node`):** The core function `aggiornaLista` utilizes the pointer-to-pointer idiom to manage and modify the list's head or intermediate links directly.
- **Sorted Linked List:** Maintains the list in lexicographical order (by 'codice fiscale') during insertion, ensuring efficient lookups and ordered output.
- **Modular Design:** Uses a separate Header (`.h`) and Implementation (`.c`) file for the Abstract Data Type (ADT).
- **Makefile:** Utilizes a custom Makefile for clean compilation and dependency management.

## Project Files
| File | Description |
| :--- | :--- |
| `main.c` | Handles command-line arguments, file I/O (binary), and calls ADT functions. |
| `listaPersone.h` | Header for the Person List ADT, defining structures (`Persona`, `Record`, `Nodo`) and function prototypes. |
| `listaPersone.c` | Implementation of list operations (`nuovaLista`, `aggiornaLista`, `stampaLista`). |
| `Makefile` | Manages compilation into the `greenpass` executable. |

## Build and Execution

### Prerequisites
The project is compiled using the GNU Compiler Collection (GCC). It has been tested and verified in a Linux/WSL environment.

### Build
Use the provided Makefile for a clean, single-command compilation process:
```
make
```
(This command generates the main.o and listaPersone.o object files and links them to create the final executable named greenpass.)

### Execution
The program requires the path to the binary data file (eventi.dat) as the sole command-line argument. The output is a list of individuals, sorted lexicographically by Codice Fiscale, showing their recorded immunity events.
```
./greenpass eventi.dat./greenpass eventi.dat.
```

### Expected Output (Sorted):
```
Codice Fiscale   Status
BLQLRW60T55A690A tampone, vaccino
BRMPWN64B04C094E tampone, vaccino
FDIWTR89S26H438B tampone, vaccino
KGTVFL96B65E715S tampone, vaccino
KLMLGB30P51C699Q tampone
MJFNVF56B13A870S vaccino
MSMSDB71P66F839O tampone, vaccino
WDTBCR34E05I626F vaccino
```
(Note: The list is generated dynamically by processing an unsorted binary file and inserting records into a lexicographically ordered linked list.)
