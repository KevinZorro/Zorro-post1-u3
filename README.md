# tienda-patrones-estructurales

Proyecto Spring Boot que implementa los patrones estructurales **Adapter** y
**Composite** en el contexto de una tienda virtual.

## Patrones Aplicados

### Adapter
Normaliza las APIs incompatibles de PayPal y Stripe hacia la interfaz interna
`PasarelaPago`. El sistema nunca depende de las clases externas directamente.

| Participante       | Clase                    |
|--------------------|--------------------------|
| Target             | `PasarelaPago` (interfaz)|
| Adaptee 1          | `PayPalAPI`              |
| Adaptee 2          | `StripeAPI`              |
| Adapter 1          | `PayPalAdapter`          |
| Adapter 2          | `StripeAdapter`          |

### Composite
Modela el catálogo de productos con categorías anidadas
(Catálogo → Electrónica → Computadores → Laptops). La interfaz `ItemCatalogo`
permite tratar hojas (`Producto`) y nodos (`Categoria`) de forma uniforme.

| Participante | Clase           |
|--------------|-----------------|
| Component    | `ItemCatalogo`  |
| Leaf         | `Producto`      |
| Composite    | `Categoria`     |

## Requisitos

- Java 17+
- Maven 3.8+

## Ejecución

```bash
# Clonar el repositorio
git clone https://github.com/<usuario>/apellido-post1-u3.git
cd apellido-post1-u3

# Compilar y empaquetar
mvn clean package

# Ejecutar
mvn spring-boot:run
```

## Pruebas

```bash
mvn test
```

Salida esperada: `BUILD SUCCESS` con 4 tests pasando.

## Salida de Consola Esperada

==============================
CATÁLOGO DE PRODUCTOS
==============================
[Catálogo General] → Total: $12,115,000
[Electrónica] → Total: $11,900,000
[Computadores] → Total: $10,700,000
- Laptop Dell XPS 15 — $4,500,000
- MacBook Air M3 — $6,200,000
- Audífonos Sony WH-1000XM5 — $1,200,000
[Libros Técnicos] → Total: $215,000
- Clean Code — Robert Martin — $95,000
- Design Patterns — GoF — $120,000

==============================
PROCESANDO COMPRA
==============================
Procesando pago con: Stripe
Stripe: cobro de 450000000 centavos [COP]
Estado del pago: APROBADO ✓
Pago exitoso: true


## Capturas de Pantalla

Ejecución
<img width="956" height="348" alt="image" src="https://github.com/user-attachments/assets/60c2d411-1bf4-4c23-a3a1-094a612331ac" />

Comando mvn clean package
<img width="957" height="464" alt="image" src="https://github.com/user-attachments/assets/555d51c1-f9a5-49af-a495-5b998ea24e3b" />




