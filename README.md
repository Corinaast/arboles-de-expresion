# Árboles binarios y árboles de expresión

Aplicación de escritorio que construye un **árbol de expresión** a partir de una expresión infija y un **árbol binario de búsqueda** a partir de números enteros, con recorridos y visualización gráfica de la estructura.

![Java](https://img.shields.io/badge/Java-21-007396?logo=openjdk&logoColor=white)
![Swing](https://img.shields.io/badge/Interfaz-Swing-5B8C5A)
![Estructuras de datos](https://img.shields.io/badge/Estructuras%20de%20datos-propias-4B5563)

---

## Qué hace

### 1. Árbol de expresión

- Recibe una expresión infija como `(3 + 5) * (2 - 8) / 4`.
- La convierte a notación postfija con el algoritmo de **Shunting Yard**, respetando precedencia (`+ -` < `* /` < `^`) y paréntesis.
- Construye el árbol con una pila auxiliar de nodos.
- Muestra los recorridos **inorden**, **preorden** y **postorden**.
- Dibuja el árbol con los operadores y operandos diferenciados por color.

### 2. Árbol binario de búsqueda

- Inserta enteros manteniendo la propiedad de ABB.
- Calcula **tamaño, altura y número de hojas**.
- Recorre el árbol en preorden, inorden, postorden y por niveles.
- Visualiza la estructura y permite limpiar el árbol.

## Cómo está construido

```
P2Lab1AcostaCorina/
└── src/
    ├── module-info.java              # módulo P2Lab1AcostaCorina
    ├── Executable/MainApp.java       # punto de entrada
    ├── Controller/TreeController.java
    ├── Model/
    │   ├── BinaryTree/BinaryTree.java    # inserción, búsqueda, métricas y recorridos
    │   ├── BinaryTree/Node.java
    │   ├── ExpressionTree/ExpressionTree.java   # infijo → árbol, recorridos
    │   ├── ExpressionTree/ExpressionUtils.java  # operadores y precedencia
    │   ├── ExpressionTree/TreeNode.java
    │   └── Stack/ListStack.java          # pila implementada con nodos enlazados
    └── View/
        ├── MainPanel.java
        ├── ExpressionTreePanel.java
        └── BinaryTreePanel.java
```

La pila del algoritmo de conversión **no** usa `java.util.Stack`: está implementada en `Model/Stack/ListStack.java` con nodos enlazados, que es el objetivo del laboratorio.

## Cómo ejecutarlo

### Opción 1 — IDE

Abre la carpeta `P2Lab1AcostaCorina` en NetBeans, IntelliJ IDEA o Eclipse y ejecuta `Executable.MainApp`.

### Opción 2 — línea de comandos (PowerShell)

```powershell
cd P2Lab1AcostaCorina
javac -d bin (Get-ChildItem -Recurse src -Filter *.java).FullName
java --module-path bin -m P2Lab1AcostaCorina/Executable.MainApp
```

En Bash/macOS/Linux:

```bash
cd P2Lab1AcostaCorina
javac -d bin $(find src -name "*.java")
java --module-path bin -m P2Lab1AcostaCorina/Executable.MainApp
```

## Documentación

[`P2Lab1_Informe_AcostaCorina.pdf`](P2Lab1_Informe_AcostaCorina.pdf) — informe del laboratorio con el diseño de las estructuras y los resultados.

## Autora

**Corina Acosta** — [@Corinaast](https://github.com/Corinaast)

Proyecto individual de la asignatura de **Estructuras de Datos** (ESPE).
