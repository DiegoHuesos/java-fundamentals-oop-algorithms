# Java Fundamentals, OOP, and Algorithms

Java coursework from ITAM’s *Algoritmos y Programas I* course. The repository contains independent exercises in object-oriented modeling, algorithms and data structures, file processing, and desktop interfaces.

## Build and run

You can build and run the exercises from a terminal with a JDK or import them into an IDE such as Eclipse. JDK 8 was used for the compile checks below. Build one project at a time because several exercises reuse class names.

### Terminal

Run this PowerShell example from the repository root. Change `$project` and `$main` to open another exercise. Look for `public static void main` in the source to find its entry point. The catalog identifies folders that contain only class definitions, archives, or configuration.

```powershell
$project = 'ConvertidorUnidadesGUI'
$main = 'ConvierteEjecutable'
$output = Join-Path 'build' $project
$sourceRoot = Join-Path $project 'src'
$encoding = 'UTF-8'

New-Item -ItemType Directory -Force $output | Out-Null
$sources = @(Get-ChildItem -LiteralPath $sourceRoot -Recurse -Filter '*.java' -File)
$lib = Join-Path $project 'library'
$jars = @(Get-ChildItem -LiteralPath $lib -Filter '*.jar' -File -ErrorAction SilentlyContinue)
$classPath = (@($output) + @($jars.FullName)) -join [IO.Path]::PathSeparator
javac -encoding $encoding -cp $classPath -d $output $sources.FullName
if ($LASTEXITCODE -ne 0) { throw "Compilation failed for $project" }
java -cp $classPath $main
```

For the equations example, use `Sistemas de Ecuaciones` and `GaussJordan`. For the nested exam, use `DiegoHD_Examen3/Examen` and set the encoding to `windows-1252`. Also use Windows-1252 for CineITAM, Estacionamiento1, Examen, and ExamenFinalDiego. Run file-based exercises with the working directory set to the folder containing their input files. GUI exercises require a graphical desktop.

### Eclipse

1. Open **File → Import → General → Existing Projects into Workspace** and select the folder containing the exercise’s `.project` file.
2. Select a compatible Java runtime. In **Properties → Resource**, set the source encoding to UTF-8 or Windows-1252 as noted in the terminal instructions. Add any bundled `library` JARs to **Java Build Path** if Eclipse reports a missing dependency.
3. Open the class with `main` and choose **Run As → Java Application**. For source-only exercises, create a Java project and add the exercise’s sources to it.

## Project catalog

Some projects provide classes for other exercises and have no standalone entry point.

| Project | What it does |
| --- | --- |
| [AgenciaAutomotriz](AgenciaAutomotriz/) | Models cars and dealership sales using an array of vehicles. |
| [AndaEnBici](AndaEnBici/) | Models a bicycle and exercises its behavior from the console. |
| [ArreglosLab](ArreglosLab/) | Practices operations on arrays in a console exercise. |
| [Automoviles](Automoviles/) | Models an automobile and exercises it with console input. |
| [Banco](Banco/) | Defines a card class for a bank modeling exercise. |
| [CadenasManejador](CadenasManejador/) | Practices string processing in an exercise that includes a person model. |
| [Calc](Calc/) | Implements a desktop calculator with a Swing view and controller. |
| [Calculadora](Calculadora/) | Provides basic and trigonometric calculators and includes ArrayList practice. |
| [Calculator](Calculator/) | Implements another desktop calculator with a Swing view and controller. |
| [CientificoMatematico](CientificoMatematico/) | Models a scientist and evaluates number properties and mathematical functions. |
| [CineITAM](CineITAM/) | Models cinema ticket purchases with a Swing interface, file input, arrays, and ArrayList. |
| [Compania](Compania/) | Models a company and processes information entered at the console using arrays. |
| [Company](Company/) | Models company expenses and includes console and file-driven examples that use arrays and matrices. |
| [ConvertidorMillasAKms](ConvertidorMillasAKms/) | Converts miles to kilometers through a Swing desktop interface. |
| [ConvertidorUnidadesGUI](ConvertidorUnidadesGUI/) | Converts inches to centimeters through a desktop interface using Swing and AWT. |
| [CuentaBancaria](CuentaBancaria/) | Models a bank account and demonstrates its operations. |
| [Cuidamos tu salud S.A.  de C.V](Cuidamos%20tu%20salud%20S.A.%20%20de%20C.V/) | Models doctors and a hospital using an ArrayList. |
| [Curso](Curso/) | Defines a course class for an object-oriented exercise. |
| [DatosAlumnos](DatosAlumnos/) | Models student records and reads student information from the console. |
| [DiegoHD_Examen3](DiegoHD_Examen3/) | Contains a nested Eclipse exam project with lottery simulation and array-processing exercises. |
| [EjemploArchivos](EjemploArchivos/) | Demonstrates reading data from a file with Scanner. |
| [Ejercicio6](Ejercicio6/) | Generates a sum of consecutive odd numbers for a cube using Nicomachus’s identity. |
| [Encriptado](Encriptado/) | Practices text encoding with arrays. |
| [encuestaElecciones](encuestaElecciones/) | Processes election survey inputs from the console. |
| [Estacionamiento](Estacionamiento/) | Models a parking lot with vehicle objects and a two-dimensional array. |
| [Estacionamiento1](Estacionamiento1/) | Contains a second parking-lot exercise that stores vehicles in a two-dimensional array. |
| [Estudio1](Estudio1/) | Contains an early console exercise stored in Perro.java with a Celular constructor declaration. |
| [Examen](Examen/) | Collects exam exercises for a lottery simulation and matrix operations using arrays and ArrayList. |
| [Examen2](Examen2/) | Analyzes words and models a rotisserie menu using arrays and ArrayList. |
| [ExamenDiegoHD](ExamenDiegoHD/) | Models a tourism package and exercises it with console input. |
| [ExamenFinalDiego](ExamenFinalDiego/) | Combines an intelligence-agency exercise and a file-processing Swing GUI with matrix operations. |
| [ExamenMildred](ExamenMildred/) | Adds repeated array values to an ArrayList. |
| [Fabrica](Fabrica/) | Calculates rug material use and pricing with console input and an ArrayList. |
| [Fiesta](Fiesta/) | Models a party and its guests using an array. |
| [FiestaLupita](FiestaLupita/) | Contains another party and guest-list exercise using an array. |
| [Fruteria](Fruteria/) | Models fruit and demonstrates a fruit-shop scenario. |
| [GaleriaDeArte](GaleriaDeArte/) | Defines an artwork model for an art gallery exercise. |
| [Geometría](Geometr%C3%ADa/) | Computes geometric measurements using circle and rectangle models. |
| [GravityBox](GravityBox/) | Reorders columns of cubes by sorting their heights in an array. |
| [HospitalITAM](HospitalITAM/) | Models a hospital and doctors using arrays and ArrayList. |
| [Laboratorio](Laboratorio/) | Computes array unions and removes duplicate values using arrays and ArrayList. |
| [leeReaccion](leeReaccion/) | Contains Eclipse project configuration for a reaction-reading exercise. |
| [LEGO](LEGO/) | Models a LEGO plant and machine states using an array. |
| [ManejadorArreglos](ManejadorArreglos/) | Contains helper methods for array processing. |
| [ManejadorArreglosIrma](ManejadorArreglosIrma/) | Demonstrates array operations with generic helpers and ArrayList. |
| [MatricesLaboratorio](MatricesLaboratorio/) | Processes student data in a matrix-based lab exercise. |
| [Matriz](Matriz/) | Provides matrix operations and a console driver for generic and numeric matrices. |
| [Nutriologo](Nutriologo/) | Models a person and reads data for a nutrition exercise from the console. |
| [OficinaGubernamental](OficinaGubernamental/) | Uses arrays to compare state populations and compute national statistics. |
| [OperacionesMatematicas](OperacionesMatematicas/) | Runs static mathematical functions with console input. |
| [Panaderia](Panaderia/) | Contains Eclipse project configuration for a bakery exercise. |
| [Persona](Persona/) | Contains Eclipse project configuration for a person-modeling exercise. |
| [PracticaExamenFinal](PracticaExamenFinal/) | Pairs an adviser-management Swing GUI with an ordered ArrayList. |
| [Pre-2Examen](Pre-2Examen/) | Compares arrays for exact equality and equality under circular rotation. |
| [PreExamEstacionamiento](PreExamEstacionamiento/) | Models a parking lot with vehicle and person objects, arrays, and ArrayList. |
| [promCarrera](promCarrera/) | Calculates a degree-program average from console input. |
| [Repaso3](Repaso3/) | Practices removing duplicate values with arrays and ArrayList. |
| [SistemaMeteorológicoNacional](SistemaMeteorol%C3%B3gicoNacional/) | Processes weather information entered through the console. |
| [Sistemas de Ecuaciones](Sistemas%20de%20Ecuaciones/) | Demonstrates Gauss–Jordan elimination, Cramer’s rule, and chemical equation exercises using matrices and bundled JARs. |
| [Tarea](Tarea/) | Sorts an array in ascending order and searches for a value in the sorted array. |
| [TareasExtrasDiegoHD](TareasExtrasDiegoHD/) | Collects ZIP archives of extra coursework. |
| [TarjetaDeCredito](TarjetaDeCredito/) | Models a credit card and exercises its operations from the console. |
| [Vivero](Vivero/) | Models a plant nursery and stores plant objects in an array. |
| [Zoologico](Zoologico/) | Models a zoo and snakes using a two-dimensional array. |
