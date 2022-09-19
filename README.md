# introduction a la programación


1. ¿Qué es un lenguaje de programación?
      
    Es una forma de comunicarse con un dispositivo como un ordenador, movil, etc.
        
    Básicamente se dividen en dos tipos:
    - Lenguajes de alto nivel
        - Java
        - C#
        - C++
        - TypeScript
    - Lenguajes de bajo nivel
        - Lenguaje ensamblador
        - Lenguaje máquina

    Los lenguajes de alto nivel son más cercanos al lenguaje natural de los seres humanos y los de bajo nivel son más cercanos al lenguaje de las máquinas.

    - **Ejemplo lenguaje de alto nivel (typescript)**
    
    ![Ejemplo lenguaje de alto nivel](img/1.png "Ejemplo lenguaje de alto nivel")
    
    - **Ejemplo lenguaje de bajo nivel (ensamblador)**
    
    ![Ejemplo lenguaje de alto nivel](img/2.png "Ejemplo lenguaje de alto nivel")
    
2. ¿Lenguajes compilados o interpretados?

    - **Los lenguajes compilados** como C++ son traducidos directamente al lenguaje máquina.

    - **Los lenguajes interpretados** como javascript son traducidos a lenguaje máquina por un interprete como **node**.

    > Java es un lenguaje de alto nivel, compilado y interpretado.

3. ¿Qué es node?

    Es un entorno en tiempo de ejecución multiplataforma. Para ser más claros, permite la ejecución del código JavaScript en cualquier entorno multiplataforma.

4. ¿Qué es JavaScript?

    Es un lenguaje de programación de alto nivel interpretado, debilmente tipado y dinámico.

5. ¿Qué es TypeScript?

    Es un lenguaje de programación de alto nivel interpretado. Además de ser un "superset" de JavaScript, es decir, una mejor versión de JavaScript que añade tipado estático y objetos basados en clase.

6. ¿Qué es la programación orientada a objetos (POO)?

    Es un paradigma de la programación donde se organiza el código en unidades domindas clases, de las cuales se crean objetos que se relacionan entre si para conseguir los objetivos de la aplicación. Es decir, intenta evitar tener un código con pura lógica y de esta manera estructurar mejor nuestro dominio en clases.

7. ¿Qué es Visual Studio Code?

    Es un entorno de desarrollo que permite editar un código fuente.

8. Antes de empezar

    8.1 Instalar [Node](https://nodejs.org/es/) interprete de JavaScript.

    8.2 Instalar TypeScript con `npm install -g typescript` en nuestra terminal.

    8.3 Instalar [Visual studio code](https://code.visualstudio.com/download) IDE para el desarrollo del código.

9. Nuestro primer "Hola mundo"

    9.1 Abrimos el terminal y ejecutamos `mkdir typescript-hello-world` para crear una carpeta para el proyecto.

    9.2 Abrimos Visual Studio code y en las opciones `archivo` -> `abrir carpeta` seleccionamos la carpeta que acabamos de crear.

    9.3 Creamos un nuevo fichero llamado `helloWorld.ts` desde el menú.
    ![Ejemplo lenguaje de alto nivel](img/3.png "Ejemplo lenguaje de alto nivel")

    9.4 Añadimos nuestro primer "Hola mundo" en el fichero `helloWorld.ts`
    ```    
    const helloWorld  = "Hello world"
    console.log(helloWorld)
    ```

    9.5 Compilamos/transpilamos código TypeScript a JavaScript con el siguiente comando en nuestra terminal `tsc *.ts`. El resultado es un fichero `helloWorld.js`.

    9.6 Ejecutamos nuestro código con `node helloWorld.js`

10. Estructurar mejor nuestro código

    Nuestro objetivo será automatizar las compilaciones.

    10.1 En el directorio de nuestro proyecto creamos un fichero llamado `tsconfig.json` con el siguiente contenido:
    ```
        {
            "compilerOptions": {"outDir": "out"},
            "include": [
                "src/*"
            ]
        }
    ```

    10.2 Creamos una carpeta llamada `src` y movemos el fichero `helloWorld.ts` al directorio `src`.

    10.3 Abrimos una nueva terminal en Visual Studio Code y ejecutamos el siguiente comando `tsc -w`

11. Pequeño repaso a TypeScript

    11.1 Tipo de datos

    ```
    let age: number
    let title: string
    let isEasy: boolean
    let user: {name: string, surname: string}
    let nothing: undefined
    let nullValue: null
    let multipleValue: string | number
    let array: string []
    let sum: (a:number, b:number) => number
    let anything: any

    const a: number = 1
    ```

    11.2 Funciones

    ```
    function minus(a: number, b: number): number {
        return a-b
    }

    function toDoSomthing(a: number, b: number): void {
        console.log(a+b)
    }

    function defaultParameter(a: number, b: number = 2): void {
        console.log(a+b)
    }

    function transform(operation: () => number): number {
        return operation()
    }
    ```

    11.3 Interfaces

    ```
    interface Run {
        run(): string
    }
    ```

    10.4 Clase abstracta

    ```
    abstract class Animal implements Run {
        name: string
        
        run(): string {
            return `${this.name} and i can run very fast!}`
        }

        abstract sayGoodbay(): string
    }
    ```

    11.5 Clase

    ```
    export class Dog extends Animal {
        name: string = 'I am a Dog'

        sayGoodbay(): string {
            return `${this.name} goodbay!`
        }
    }

    export class Cat extends Animal {
        name: string = 'I am a Cat'

        sayGoodbay(): string {
            return `${this.name} and goodbay :(`
        }
    }
    ```
    
    11.6 Genéricos

    ```
    interface Iterable<T> {
        list: T []
    }

    abstract class Collection<T> {
        list: T []
    }

    class List<T> {
        list: T []
    }

    function generic<A, B>(argument: A, f: (a: A)=> B): B {
        return f(argument)
    }

    ```
12. Caso práctico
    
    Seguir las instrucciones.

13. Deberes
    
    
    
