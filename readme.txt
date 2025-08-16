# Examen1Back2 – Resumen

**Proyecto:** API backend con Spring Boot, JPA y MySQL para manejar **Usuario, Docente y Curso**.  
Relaciones:  
- Usuario ↔ Docente (OneToOne)  
- Docente ↔ Curso (OneToMany)  

---

## Errores corregidos
- @I → @Id, @Ge → @GeneratedValue.  
- Campos sin ; corregidos.  
- FK de Docente ahora apunta a id_usuario (antes apuntaba mal).  
- Se creó enum TipoUsuario.  
- Se eliminaron archivos duplicados (1)(2)(3).java y application(1)(2).properties.  
- Se agregaron @JsonManagedReference / @JsonBackReference para evitar recursión.  
- Campos con tilde (contraseña) renombrados a contrasena.  

---

## Conexión a BD
1. Crear BD:
   ```sql
   CREATE DATABASE develop_db;
   ```
2. application.properties:
   ```
   spring.datasource.url=jdbc:mysql://localhost:3306/develop_db
   spring.datasource.username=root
   spring.datasource.password=
   spring.jpa.hibernate.ddl-auto=update
   ```
3. Levantar MySQL y correr Examen1Back2Application.  

---

## Recomendaciones
- No usar tildes ni ñ en nombres.  
- Verificar siempre que el referencedColumnName exista en la entidad destino.  
- Borrar duplicados antes de compilar.  
- Usar fetch=LAZY y referencias JSON para evitar loops.  
