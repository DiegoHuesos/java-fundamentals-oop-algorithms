# Java Fundamentals, OOP, and Algorithms

Java coursework from ITAM covering arrays, matrices, introductory algorithms, object-oriented modeling, and desktop interfaces. Each folder is a separate exercise or Eclipse project.

## Where to start

- [ArreglosLab](ArreglosLab/) — Array exercises.
- [CineITAM](CineITAM/) — An object-oriented cinema exercise.
- [ConvertidorUnidadesGUI](ConvertidorUnidadesGUI/) — Convert inches to centimeters. Press Enter or click **Convierte**.

## Build and run

Use a JDK with `javac` and `java` on your PATH. Eclipse is optional. From the repository root, run the following PowerShell commands. The examples were compiled with JDK 8.

```powershell
foreach ($project in @('ArreglosLab', 'CineITAM', 'ConvertidorUnidadesGUI')) {
    $output = Join-Path 'build' $project
    New-Item -ItemType Directory -Force $output | Out-Null
    $sources = (Get-ChildItem (Join-Path $project 'src') -Recurse -Filter '*.java').FullName
    $encoding = if ($project -eq 'CineITAM') { 'windows-1252' } else { 'UTF-8' }
    javac -encoding $encoding -d $output $sources
    if ($LASTEXITCODE -ne 0) { throw "Compilation failed for $project" }
}
java -cp build/ConvertidorUnidadesGUI ConvierteEjecutable
```

The converter requires a graphical desktop. The commands cover the three examples above.

## Systems of equations

The [Sistemas de Ecuaciones](Sistemas%20de%20Ecuaciones/) exercises cover Gauss–Jordan elimination, Cramer's rule, and chemical equations. Build the Java files in its src folder with the Jama and chembal JARs in its library folder on the classpath. Run the GaussJordan class to see the built-in example.
