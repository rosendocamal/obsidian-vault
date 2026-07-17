---
title: "Algoritmos de Booth para la multiplicación y división en binario"
source: "algoritmos_booth_multiplicación_división.pdf"
type: homework
---

# Algoritmos de Booth para la multiplicación y división en binario

Rosendo Camal
22 de noviembre de 2025

## Introducción

El algoritmo de Booth es un método de multiplicación binaria, inventado por Andrew Donald Booth en 1950, que optimiza el proceso al reducir el número de operaciones de suma y resta. Su principal ventaja es que analiza secuencias de bits para simplificar la multiplicación, siendo particularmente eficiente con números que contienen largas cadenas de ceros y unos. Esto lo convirtió en un método fundamental y muy estudiado en computación.

## Andrew Donald Booth

Andrew Donald Booth, científico británico nacido en 1918, fue pionero en informática al crear el algoritmo de Booth (en 1950), un método eficiente para multiplicar números binarios con signo mediante el complemento a dos. Su aporte se convirtió en pieza clave en el diseño de las unidades aritmético-lógicas (ALU) de los procesadores.

Además de crear su algoritmo, Booth diseñó el tambor magnético, uno de los primeros dispositivos de almacenamiento digital y precursor de la memoria RAM. Colaboró con figuras como John von Neumann en proyectos de traducción automática y trabajó en instituciones como el Birkbeck College, la Universidad de Saskatchewan y la Lakehead University. Falleció en 2009 en Canadá, dejando un legado clave en la historia de la computación.

## Algoritmo de Booth (multiplicación)

El algoritmo de Booth es un método para multiplicar números binarios con signo. Utiliza el complemento a dos y evalúa pares de bits del multiplicador para decidir si sumar, restar o desplazar, logrando una multiplicación más eficiente en los procesadores.

### Pasos del Algoritmo de Booth

1. **Complemento a dos**: convertir los números (positivos y negativos).
2. **Revisar pares de bits del multiplicador:**
   - Si **01** → sumar el multiplicando.
   - Si **10** → restar el multiplicando.
   - Si **00** o **11** → no hacer nada, solo desplazar.
3. **Desplazamiento**: mover los registros a la derecha, como correr los dígitos en una calculadora.
4. **Repetir** hasta recorrer todos los bits.

### Ejemplo

#### 1. Preparar los números:

- Representar 10 en binario como 01010.
- Representar 3 en binario como 00011.
- Mantener ambos en positivo, sin necesidad de convertir a complemento a dos.

#### 2. Aplicar las reglas del algoritmo de Booth:

- Observar siempre el último bit del multiplicador (Q0) junto con el bit auxiliar Q₋₁.
- Detectar 01 → sumar el multiplicando.
- Detectar 10 → restar el multiplicando.
- Detectar 00 o 11 → no realizar operación.
- Desplazar a la derecha el registro completo después de cada evaluación.

#### 3. Ejecutar las repeticiones:

- 3.1. Detectar par (Q0=1, Q₋₁=0) → 01 → sumar 10 → desplazar a la derecha.
- 3.2. Detectar par (Q0=1, Q₋₁=1) → 11 → no realizar operación → desplazar.
- 3.3. Detectar par (Q0=0, Q₋₁=1) → 10 → restar 10 → desplazar.
- 3.4. Detectar par (Q0=0, Q₋₁=0) → 00 → no realizar operación → desplazar.

#### 4. Resultado final:

Concluir el proceso al recorrer todos los bits. Registrar el resultado como 11110 en binario. Interpretar el valor como 30 en decimal.

### Ventajas, desventajas y aplicaciones

| Ventajas | Desventajas | Aplicaciones |
|----------|-------------|--------------|
| Menos operaciones en secuencias largas de bits. | Mayor complejidad de implementación frente a métodos básicos. | Procesadores |
| Eficiente con números positivos y negativos. | Requiere control preciso de registros y desplazamientos. | Criptografía |
| Aplicado en procesadores modernos. | | Educación informática y computación |

## Algoritmo de División

El algoritmo de división es un método para dividir números en binario de forma similar a la división larga en decimal. Consiste en ir restando el divisor al dividendo paso a paso, desplazando los bits y construyendo el cociente y el residuo hasta completar el proceso. Es la base de cómo los procesadores realizan operaciones de división.

### Pasos del Algoritmo de la División

1. **Representar** los números en binario (dividendo y divisor).
2. **Restar y desplazar**: compara el divisor con partes del dividendo.
   - Si se puede restar → coloca un 1 en el cociente.
   - Si no se puede → coloca un 0.
3. **Repetir** el proceso hasta recorrer todos los bits.
4. **Resultado final**: se obtiene el cociente y el residuo.

### Ejemplo: 10 ÷ 3

1. **Representar en binario**: 10 = 1010 y 3 = 0011.

2. **Proceso de división:**
   - Comparar divisor 0011 (3) con dividendo 1010 (10).
   - Sí cabe, entonces restar: $1010 - 0011 = 0111$. Sumar un 0001 en el cociente.
   - Ahora se tiene como dividendo el 0111.
   - Comparar otra vez: $0111 > 0011$.
   - Sí cabe, restar: $0111 - 0011 = 0100$. Sumar 0001 en el cociente.
   - Comparar otra vez: $0100 > 0011$.
   - Sí cabe, restar: $0100 - 0011 = 0001$. Sumar 0001 en el cociente.
   - Comparar otra vez: $0001 < 0011$.
   - No cabe, sumar 0000 en el cociente y finalizar la división.

3. **Resultado final:**
   - Cociente: 0011 (3 en decimal)
   - Residuo: 0001 (1 en decimal)

4. El algoritmo muestra que $10 \div 3 = 3$ con residuo 1.

### Ventajas, desventajas y aplicaciones

| Ventajas | Desventajas | Aplicaciones |
|----------|-------------|--------------|
| Permite dividir directamente en binario. | Requiere varios ciclos de desplazamiento y resta, lo que puede ser lento. | ALU de procesadores |
| Sistemático y repetitivo, fácil de implementar en hardware. | Es más complejo que la multiplicación. | Compiladores aritméticos |
| Es completo, ya que produce el cociente y el residuo. | Puede ser ineficiente para números grandes sin optimizaciones. | Criptografía avanzada |

## Conclusión

En síntesis, tanto el algoritmo de Booth como el de división binaria contribuyeron de manera decisiva a simplificar y optimizar los cálculos en sistemas digitales, al aprovechar las secuencias de 1s y 0s y aplicar reglas basadas en patrones. Gracias a este enfoque, se redujo la necesidad de operar bit por bit, logrando procesos más eficientes y ordenados en la multiplicación y división de números binarios con signo.

## Cibergrafía

- Ayuso Pérez, Jesús. 29 de junio de 2017. Algoritmo de Booth en operaciones de exponenciación modular. 3ciencias. Recuperado el 18 de noviembre de 2025 de https://3ciencias.com/wp-content/uploads/2017/06/ART-1-2.pdf
- Benemérita Universidad Autónoma de Puebla. (s. f.). Los sistemas de numeración. Recuperado el 18 de noviembre de 2025 de https://www.cs.buap.mx/~andrex/ensamblador/sistemas-de-numeracion.pdf
- Kulrativid, Jetnipit. 11 de julio de 2022. Booth Algorithm. Medium. Recuperado el 18 de noviembre de 2025 de https://medium.com/@jetnipit54/booth-algorithm-e6b8a6c5b8d
- Peña Vergara, Alberto. Abril de 2013. Apuntes de Teledetección: Entendiendo los sistemas numéricos de los computadores. Centro de Información de Recursos Naturales. Recuperado el 18 de noviembre de 2025 de https://bibliotecadigital.ciren.cl/bitstreams/41ea0e6e-5801-4214-ac33-e92c7274106a/download
- Universitat de València. (s. f.). Aritmética y representación de la información en el computador. Recuperado el 18 de noviembre de 2025 de https://informatica.uv.es/docencia/fguia/TI/Libro/PDFs/CAPI4.pdf
- Wikipedia, la enciclopedia libre. (s. f.). Andrew Donald Booth. Recuperado el 19 de noviembre de 2025 de https://en.wikipedia.org/wiki/Andrew_Donald_Booth
