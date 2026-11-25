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

For the equations example, use `Sistemas de Ecuaciones` and `GaussJordan`. For the nested exam, use `DiegoHD_Examen3/Examen` and set the encoding to `windows-1252`. The catalog marks the other Windows-1252 projects. Run file-based exercises with the working directory set to the folder containing their input files. GUI exercises require a graphical desktop.

### Eclipse

1. Open **File → Import → General → Existing Projects into Workspace** and select the folder containing the exercise’s `.project` file.
2. Select a compatible Java runtime. In **Properties → Resource**, set the source encoding to the value shown in the catalog. Add any bundled `library` JARs to **Java Build Path** if Eclipse reports a missing dependency.
3. Open the class with `main` and choose **Run As → Java Application**. For source-only exercises, create a Java project and add the exercise’s sources to it.

## Project catalog

The build column records isolated JDK 8 compilation, which does not exercise every runtime path. Some projects compile as classes for use in other exercises and have no entry point.

| Project | What it does | Build check |
| --- | --- | --- |
| [a](a/) | Contains a historical Eclipse WindowBuilder update site with plugin JARs. | No Java source |
| [AgenciaAutomotriz](AgenciaAutomotriz/) | Models cars and dealership sales using an array of vehicles. | Compiles (UTF-8) |
| [AndaEnBici](AndaEnBici/) | Models a bicycle and exercises its behavior from the console. | Compiles (UTF-8) |
| [ArreglosLab](ArreglosLab/) | Practices operations on arrays in a console exercise. | Compiles (UTF-8) |
| [Automoviles](Automoviles/) | Models an automobile and exercises it with console input. | Compiles (UTF-8) |
| [Banco](Banco/) | Defines a card class for a bank modeling exercise. | Compiles (UTF-8) |
| [CadenasManejador](CadenasManejador/) | Practices string processing in an exercise that includes a person model. | Compiles (UTF-8) |
| [Calc](Calc/) | Implements a desktop calculator with a Swing view and controller. | Compiles (UTF-8) |
| [Calculadora](Calculadora/) | Provides basic and trigonometric calculators and includes ArrayList practice. | Compiles (UTF-8) |
| [Calculator](Calculator/) | Implements another desktop calculator with a Swing view and controller. | Compiles (UTF-8) |
| [CientificoMatematico](CientificoMatematico/) | Models a scientist and evaluates number properties and mathematical functions. | Compiles (UTF-8) |
| [CineITAM](CineITAM/) | Models cinema ticket purchases with a Swing interface, file input, arrays, and ArrayList. | Compiles (windows-1252) |
| [Compania](Compania/) | Models a company and processes information entered at the console using arrays. | Fails to compile (unresolved symbol) |
| [Company](Company/) | Models company expenses and includes console and file-driven examples that use arrays and matrices. | Fails to compile (unresolved symbol) |
| [ConvertidorMillasAKms](ConvertidorMillasAKms/) | Converts miles to kilometers through a Swing desktop interface. | Compiles (UTF-8) |
| [ConvertidorUnidadesGUI](ConvertidorUnidadesGUI/) | Converts inches to centimeters through a desktop interface using Swing and AWT. | Compiles (UTF-8) |
| [CuentaBancaria](CuentaBancaria/) | Models a bank account and demonstrates its operations. | Compiles (UTF-8) |
| [Cuidamos tu salud S.A.  de C.V](Cuidamos%20tu%20salud%20S.A.%20%20de%20C.V/) | Models doctors and a hospital using an ArrayList. | Compiles (UTF-8) |
| [Curso](Curso/) | Defines a course class for an object-oriented exercise. | Compiles (UTF-8) |
| [DatosAlumnos](DatosAlumnos/) | Models student records and reads student information from the console. | Compiles (UTF-8) |
| [DiegoHD_Examen3](DiegoHD_Examen3/) | Contains a nested Eclipse exam project with lottery simulation and array-processing exercises. | Compiles (windows-1252) |
| [EjemploArchivos](EjemploArchivos/) | Demonstrates reading data from a file with Scanner. | Compiles (UTF-8) |
| [Ejercicio6](Ejercicio6/) | Generates a sum of consecutive odd numbers for a cube using Nicomachus’s identity. | Compiles (UTF-8) |
| [Encriptado](Encriptado/) | Practices text encoding with arrays. | Compiles (UTF-8) |
| [encuestaElecciones](encuestaElecciones/) | Processes election survey inputs from the console. | Compiles (UTF-8) |
| [Estacionamiento](Estacionamiento/) | Models a parking lot with vehicle objects and a two-dimensional array. | Compiles (UTF-8) |
| [Estacionamiento1](Estacionamiento1/) | Contains a second parking-lot exercise that stores vehicles in a two-dimensional array. | Compiles (windows-1252) |
| [Estudio1](Estudio1/) | Contains an early console exercise stored in Perro.java with a Celular constructor declaration. | Fails to compile (class and filename differ) |
| [Examen](Examen/) | Collects exam exercises for a lottery simulation and matrix operations using arrays and ArrayList. | Compiles (windows-1252) |
| [Examen2](Examen2/) | Analyzes words and models a rotisserie menu using arrays and ArrayList. | Compiles (UTF-8) |
| [ExamenDiegoHD](ExamenDiegoHD/) | Models a tourism package and exercises it with console input. | Compiles (UTF-8) |
| [ExamenFinalDiego](ExamenFinalDiego/) | Combines an intelligence-agency exercise and a file-processing Swing GUI with matrix operations. | Compiles (windows-1252) |
| [ExamenMildred](ExamenMildred/) | Adds repeated array values to an ArrayList. | Compiles (UTF-8) |
| [Fabrica](Fabrica/) | Calculates rug material use and pricing with console input and an ArrayList. | Fails to compile (unresolved symbol) |
| [Fiesta](Fiesta/) | Models a party and its guests using an array. | Compiles (UTF-8) |
| [FiestaLupita](FiestaLupita/) | Contains another party and guest-list exercise using an array. | Compiles (UTF-8) |
| [Fruteria](Fruteria/) | Models fruit and demonstrates a fruit-shop scenario. | Compiles (UTF-8) |
| [GaleriaDeArte](GaleriaDeArte/) | Defines an artwork model for an art gallery exercise. | Compiles (UTF-8) |
| [Geometría](Geometr%C3%ADa/) | Computes geometric measurements using circle and rectangle models. | Compiles (UTF-8) |
| [GravityBox](GravityBox/) | Reorders columns of cubes by sorting their heights in an array. | Compiles (UTF-8) |
| [HospitalITAM](HospitalITAM/) | Models a hospital and doctors using arrays and ArrayList. | Compiles (UTF-8) |
| [Laboratorio](Laboratorio/) | Computes array unions and removes duplicate values using arrays and ArrayList. | Compiles (UTF-8) |
| [leeReaccion](leeReaccion/) | Contains Eclipse project configuration for a reaction-reading exercise. | No Java source |
| [LEGO](LEGO/) | Models a LEGO plant and machine states using an array. | Compiles (UTF-8) |
| [ManejadorArreglos](ManejadorArreglos/) | Contains helper methods for array processing. | Compiles (UTF-8) |
| [ManejadorArreglosIrma](ManejadorArreglosIrma/) | Demonstrates array operations with generic helpers and ArrayList. | Compiles (UTF-8) |
| [MatricesLaboratorio](MatricesLaboratorio/) | Processes student data in a matrix-based lab exercise. | Compiles (UTF-8) |
| [Matriz](Matriz/) | Provides matrix operations and a console driver for generic and numeric matrices. | Compiles (UTF-8) |
| [Nutriologo](Nutriologo/) | Models a person and reads data for a nutrition exercise from the console. | Compiles (UTF-8) |
| [OficinaGubernamental](OficinaGubernamental/) | Uses arrays to compare state populations and compute national statistics. | Compiles (UTF-8) |
| [OperacionesMatematicas](OperacionesMatematicas/) | Runs static mathematical functions with console input. | Compiles (UTF-8) |
| [Panaderia](Panaderia/) | Contains Eclipse project configuration for a bakery exercise. | No Java source |
| [Persona](Persona/) | Contains Eclipse project configuration for a person-modeling exercise. | No Java source |
| [PracticaExamenFinal](PracticaExamenFinal/) | Pairs an adviser-management Swing GUI with an ordered ArrayList. | Compiles (UTF-8) |
| [Pre-2Examen](Pre-2Examen/) | Compares arrays for exact equality and equality under circular rotation. | Compiles (UTF-8) |
| [PreExamEstacionamiento](PreExamEstacionamiento/) | Models a parking lot with vehicle and person objects, arrays, and ArrayList. | Compiles (UTF-8) |
| [promCarrera](promCarrera/) | Calculates a degree-program average from console input. | Compiles (UTF-8) |
| [Repaso3](Repaso3/) | Practices removing duplicate values with arrays and ArrayList. | Compiles (UTF-8) |
| [SistemaMeteorológicoNacional](SistemaMeteorol%C3%B3gicoNacional/) | Processes weather information entered through the console. | Compiles (UTF-8) |
| [Sistemas de Ecuaciones](Sistemas%20de%20Ecuaciones/) | Demonstrates Gauss–Jordan elimination, Cramer’s rule, and chemical equation exercises using matrices and bundled JARs. | Compiles (UTF-8) |
| [Tarea](Tarea/) | Sorts an array in ascending order and searches for a value in the sorted array. | Compiles (UTF-8) |
| [TareasExtrasDiegoHD](TareasExtrasDiegoHD/) | Collects ZIP archives of extra coursework. | No Java source |
| [TarjetaDeCredito](TarjetaDeCredito/) | Models a credit card and exercises its operations from the console. | Compiles (UTF-8) |
| [Vivero](Vivero/) | Models a plant nursery and stores plant objects in an array. | Compiles (UTF-8) |
| [Zoologico](Zoologico/) | Models a zoo and snakes using a two-dimensional array. | Compiles (UTF-8) |

Root-level archives: [Calc.zip](Calc.zip) and [Geometría.zip](Geometr%C3%ADa.zip) are archived copies of the corresponding exercises.
