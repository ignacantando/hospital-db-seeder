<h1 align="center">🏥 Hospital DB Seeder</h1>

<p align="center">
  Script en <b>Node.js</b> que puebla y limpia una base de datos <b>PostgreSQL</b> de un hospital con datos de prueba realistas generados con <b>Faker</b>.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white" alt="Node.js" />
  <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL" />
  <img src="https://img.shields.io/badge/Faker.js-es-1f6f4a?style=for-the-badge" alt="Faker.js" />
  <img src="https://img.shields.io/badge/UNMdP-Bases%20de%20Datos-1f6f4a?style=for-the-badge" alt="UNMdP Bases de Datos" />
</p>

---

## 📌 Sobre el proyecto

Herramienta para un trabajo práctico de **bases de datos**. Sirve para probar consultas, restricciones y rendimiento sobre un modelo hospitalario con datos variados, sin cargarlos a mano.

Todo corre dentro de **transacciones** (`BEGIN` / `COMMIT` / `ROLLBACK`): si algo falla, la base queda como estaba.

## ⚙️ Qué genera

| Entidad | Detalle |
| --- | --- |
| **Sectores** | Cardiología, Pediatría, Traumatología, Neurología, Oncología |
| **Habitaciones y camas** | 20 habitaciones con piso y orientación, de 2 a 4 camas cada una |
| **Especialidades y guardias** | 6 especialidades con 3 guardias cada una |
| **Médicos y pacientes** | 30 médicos y 50 pacientes con datos en español y DNIs únicos |
| **Internaciones, rondas y recorridos** | 40 internaciones y 100 recorridos, con fechas coherentes |
| **Vacaciones y comentarios** | Para completar el modelo relacional |

La limpieza borra las tablas **en orden inverso a sus dependencias**, para no violar claves foráneas.

## 🚀 Uso

Requisitos: **Node.js 18+** y una base PostgreSQL con el esquema creado y la extensión `uuid-ossp`.

```bash
git clone https://github.com/ignacantando/hospital-db-seeder.git
cd hospital-db-seeder/host
npm install
```

Configurá la conexión (usuario, host, puerto y base) en el `Pool` al principio de `host.js`. Después:

```bash
npm run seed    # poblar la base con datos de prueba
npm run clean   # borrar todos los datos
npm run reset   # limpiar y volver a poblar
```

## 🛠️ Stack

- [`pg`](https://node-postgres.com/): cliente de PostgreSQL con *pool* de conexiones
- [`@faker-js/faker`](https://fakerjs.dev/) con *locale* `es`: datos realistas en español
- `dotenv`

## 👤 Autor

**Ignacio Cantando Flego** · [LinkedIn](https://www.linkedin.com/in/ignaciocantandoflego/) · [GitHub](https://github.com/ignacantando)
