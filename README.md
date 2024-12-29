# **Gestor de Solicitudes de Cambios**

Un sistema integral para gestionar la creación, aprobación y ejecución de solicitudes de cambios en entornos productivos. Este proyecto está diseñado para simplificar y automatizar los procesos de aprobación y seguimiento mediante tecnologías de **SAP BTP**.

---

## **Características**
- **Gestión de solicitudes:** 
  - Crear y gestionar solicitudes de cambios con campos personalizados.
  - Adjuntar documentos relacionados.
- **Flujo de aprobación:** 
  - Aprobar o rechazar solicitudes con comentarios.
  - Notificaciones automáticas para los usuarios involucrados.
- **Ejecución de solicitudes aprobadas:** 
  - Visualizar las solicitudes en una bandeja de tareas para los ejecutores.
  - Actualizar el estado al completar la ejecución.
- **Almacenamiento seguro:** 
  - Integración con **SAP HANA** para garantizar la persistencia y seguridad de los datos.
- **Automatización del flujo:** 
  - Usando **SAP Build Process Automation** para la orquestación de tareas.

---

## **Arquitectura del Proyecto**

### **Tecnologías utilizadas**
1. **Backend:** 
   - Cloud Application Programming (CAP).
   - SAP HANA como base de datos.
2. **Frontend:** 
   - SAPUI5 para una interfaz de usuario moderna y responsiva.
3. **Automatización:** 
   - SAP Build Process Automation (BPA).
4. **Gestión de documentos:** 
   - Document Management Service (DMS).
5. **Colaboración:** 
   - SAP Build Work Zone para centralizar las aplicaciones.
6. **Integración continua:** 
   - Pipelines de CI/CD usando GitHub Actions.

---

## **Estructura del Proyecto**
```plaintext
gestor-solicitudes-cambios/
├── backend/                    # Proyecto CAP
│   ├── srv/                    # Servicios CAP
│   ├── db/                     # Esquema de datos HANA
│   ├── xs-security.json        # Configuración de roles
│   └── package.json            # Dependencias CAP
├── frontend/                   # Proyecto SAPUI5
│   ├── webapp/                 # Código SAPUI5
│   ├── manifest.json           # Configuración UI5
│   └── package.json            # Dependencias UI5
├── cicd/                       # Configuración de pipelines CI/CD
│   ├── deploy_ui5.sh           # Script de despliegue para UI5
│   └── deploy_cap.sh           # Script de despliegue para CAP
└── README.md                   # Documentación del proyecto
```

---

## **Cómo ejecutar el proyecto**

### **Requisitos previos**
1. Acceso a un espacio en **SAP BTP**.
2. Node.js v16 o superior.
3. Instalar el CLI de SAP:
   ```bash
   npm install -g @sap/cds-dk
   ```

### **Pasos para ejecutar localmente**
1. **Clonar el repositorio:**
   ```bash
   git clone https://github.com/tu-usuario/gestor-solicitudes-cambios.git
   cd gestor-solicitudes-cambios
   ```

2. **Iniciar el backend:**
   ```bash
   cd backend
   npm install
   cds watch
   ```

3. **Iniciar el frontend:**
   ```bash
   cd frontend
   npm install
   ui5 serve
   ```

4. **Acceder a la aplicación:**
   - Backend: [http://localhost:4004](http://localhost:4004)
   - Frontend: [http://localhost:8080](http://localhost:8080)

---

## **Flujo de trabajo**
1. **Creación:** 
   - Un solicitante crea una solicitud desde el frontend.
   - La solicitud se guarda en la base de datos HANA.
2. **Aprobación:** 
   - El aprobador revisa la solicitud y decide aprobarla o rechazarla.
   - El flujo de BPA actualiza el estado en la base de datos.
3. **Ejecución:** 
   - El ejecutor recibe las solicitudes aprobadas y marca la ejecución como completada.

---

## **Contribución**
1. Crea un fork del repositorio.
2. Haz cambios en una nueva rama:
   ```bash
   git checkout -b feature/nueva-funcionalidad
   ```
3. Envía un pull request.

---

## **Licencia**
Este proyecto está bajo la licencia MIT. Consulta el archivo [LICENSE](LICENSE) para más detalles.
