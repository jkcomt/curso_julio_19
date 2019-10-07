<div style="text-align: justify">

# Capacitación SAPUI5, OData, HANA XS - Julio 2019

- [Capacitación SAPUI5, OData, HANA XS - Julio 2019](#Capacitaci%C3%B3n-SAPUI5-OData-HANA-XS---Julio-2019)
  - [Requisitos](#Requisitos)
  - [Enlaces útiles](#Enlaces-%C3%BAtiles)
- [SAP HANA XS](#SAP-HANA-XS)
  - [Instalación de BD HANA en SCP](#Instalaci%C3%B3n-de-BD-HANA-en-SCP)
  - [Acceso al HANA Web-based editor](#Acceso-al-HANA-Web-based-editor)
  - [Creación de servicios XSJS en HANA (1)](#Creaci%C3%B3n-de-servicios-XSJS-en-HANA-1)
    - [Servicio XSJS que retorna texto](#Servicio-XSJS-que-retorna-texto)
    - [Servicio XSJS que retorna JSON](#Servicio-XSJS-que-retorna-JSON)
  - [Creación de Tablas en HANA](#Creaci%C3%B3n-de-Tablas-en-HANA)
    - [Crear schema](#Crear-schema)
    - [Crear database definition](#Crear-database-definition)
    - [Cargar datos de prueba](#Cargar-datos-de-prueba)
  - [Creación de servicios XSJS en HANA (2)](#Creaci%C3%B3n-de-servicios-XSJS-en-HANA-2)
    - [Lectura de tabla - Resultado como texto](#Lectura-de-tabla---Resultado-como-texto)
    - [Lectura de tabla - Resultado como JSON](#Lectura-de-tabla---Resultado-como-JSON)
    - [Utilizar Sequences](#Utilizar-Sequences)
  - [Debugging en HANA](#Debugging-en-HANA)
  - [SAP HANA XS Data Services (XSDS)](#SAP-HANA-XS-Data-Services-XSDS)
    - [Importar la librería](#Importar-la-librer%C3%ADa)
    - [Lectura de registros para Unmanaged Associations](#Lectura-de-registros-para-Unmanaged-Associations)
    - [Lectura de registros para Managed Associations](#Lectura-de-registros-para-Managed-Associations)
  - [SAP HANA XS Procedures](#SAP-HANA-XS-Procedures)
    - [Llamar un Procedure desde un servicio .xsjs](#Llamar-un-Procedure-desde-un-servicio-xsjs)
  - [OData en HANA XS](#OData-en-HANA-XS)
    - [Creación de un servicio OData en HANA XS](#Creaci%C3%B3n-de-un-servicio-OData-en-HANA-XS)
    - [Extender/ampliar una operación de servicio OData en HANA XS](#Extenderampliar-una-operaci%C3%B3n-de-servicio-OData-en-HANA-XS)
    - [Usar el OData Explorer](#Usar-el-OData-Explorer)
- [OData](#OData)
  - [Parámetros OData](#Par%C3%A1metros-OData)
- [SAP Cloud Platform Workflow](#SAP-Cloud-Platform-Workflow)
  - [Pre-requisitos para usar SCP Workflow](#Pre-requisitos-para-usar-SCP-Workflow)
  - [Activar la Extensión de Workflow en SAP Web IDE](#Activar-la-Extensi%C3%B3n-de-Workflow-en-SAP-Web-IDE)
  - [Creación de un nuevo Workflow](#Creaci%C3%B3n-de-un-nuevo-Workflow)
  - [Usando los Eventos, Tasks y Gateways](#Usando-los-Eventos-Tasks-y-Gateways)
    - [Planteando la solución](#Planteando-la-soluci%C3%B3n)
    - [Modelando el workflow](#Modelando-el-workflow)
  - [Creando los formularios](#Creando-los-formularios)
  - [Desplegando los elementos Workflow](#Desplegando-los-elementos-Workflow)
  - [Creando la aplicación SAPUI5 (Gatilla el Workflow)](#Creando-la-aplicaci%C3%B3n-SAPUI5-Gatilla-el-Workflow)
  - [Desplegando y Registrando la aplicación en el Fiori Launchpad](#Desplegando-y-Registrando-la-aplicaci%C3%B3n-en-el-Fiori-Launchpad)
- [Portal Service](#Portal-Service)
- [OData en ABAP](#OData-en-ABAP)

## Requisitos

* Instalar Postman.
* Instalar SAP Logon 760.
* Instalar Google Chrome (última versión).
* Crear su usuario trial de SCP con el correo largo de everis.
* Activar BD HANA MDC en SCP Cockpit.
* Instalar Git para Windows.

## Enlaces útiles
* SAP HANA Documentation<br>
  <https://help.sap.com/viewer/product/SAP_HANA_PLATFORM/1.0.12/en-US>

* SAP HANA XS Javascript Reference<br>
  <https://help.sap.com/doc/7709218a773b4cca877b7b452025e152/2.0.00/en-US/SAP_HANA_XS_JavaScript_Reference_en.pdf>

* OData v2.0 Documentation<br>
  <https://www.odata.org/documentation/odata-version-2-0/uri-conventions/>

* SAP HANA SPS 09: New Developer Features; XSDS (XS Data Services)<br>
  <https://blogs.sap.com/2014/12/09/sap-hana-sps-09-new-developer-features-xsds-xs-data-services/>

* SAP HANA XS JavaScript API Reference<br>
  <https://help.sap.com/doc/3de842783af24336b6305a3c0223a369/1.0.12/en-US/index.html>

* SAP HANA Core Data Services (CDS) Reference<br>
  <https://help.sap.com/viewer/09b6623836854766b682356393c6c416/1.0.12/en-US>

* SAP HANA XS Data Services (xsds) API<br>
  <https://help.sap.com/doc/0422944cf5554917b5ac2c3ebf9f1974/1.0.12/en-US/sap.hana.xs.libs.dbutils.xsds.html>

* SAP Cloud Platform Workflow for Neo<br>
  <https://help.sap.com/viewer/p/WORKFLOW_SERVICE>

* SAP Cloud Platform Workflow API for Neo<br>
  <https://help.sap.com/doc/72317aec52144df8bc04798fd232a585/Cloud/en-US/wfs-core-api-docu.html#api-WorkflowInstances-v1WorkflowInstancesPost>

* SAP Icons<br>
  <https://sapui5.hana.ondemand.com/sdk/test-resources/sap/m/demokit/iconExplorer/webapp/index.html#/overview/SAP-icons>  

# SAP HANA XS
## Instalación de BD HANA en SCP
1.	Ingresar al SCP Cockpit e ir al trial Neo:<br>
https://account.hanatrial.ondemand.com/cockpit/
2.	En el Menu, desplegar la sección SAP HANA / SAP ASE.
3.	Ingresar en la opción Databases & Schemas.
4.	Presionar el botón New.
5.	En Database ID colocar:<br>
`<Usuario Corto>mdchana`
6.	En contraseña colocar:
`Everis5#eEveris5#e`
7.	Dejar las demás opciones por default.
8.	Presionar el botón Create.<br>
    ![](/img/2019-07-01-15-29-41.png)

    ***Notas:***
    * La creación puede demorar unos cuantos minutos (5-10 min).
    * En caso ocurra algún error durante la creación (CREATION FAILED), borrar la BD (puede demorar unos minutos) e intentar crearla de nuevo.
    * Si logramos una instalación correcta, deberíamos ver la BD con status STARTED:
    ![](/img/2019-07-01-15-30-59.png)

## Acceso al HANA Web-based editor
1.	Ir al HANA Administration Cockpit. Dar OK al diálogo que aparece (la primera vez se le asignan automáticamente los permisos al usuario).

1. Ir a la opción SAP HANA Web-Based Development Workbench<br>
https://\<host\>.hanatrial.ondemand.com/sap/hana/ide/ 
![](/img/2019-07-01-15-32-48.png)
3.	En caso les pida ingresar Usuario/Contraseña, usar:
<br>`SYSTEM`
<br>`Everis5#eEveris5#e`<br>
    ![](/img/2019-07-01-15-32-57.png)
4.	Ir a Security:
https://\<host\>.hanatrial.ondemand.com/sap/hana/ide/security/

5.	Crear un nuevo usuario. De preferencia, colocar como contraseña inicial:
`Everis5#eEveris5#e2`

    ***Nota:*** Cuando se ingrese por primera vez con ese usuario, cambiar la contraseña por:<br>
    `Everis5#eEveris5#e`

6.	Agregar los siguientes roles en Granted Roles:

    ![](/img/2019-07-01-15-33-05.png)
7.	Agregar los siguientes Roles en Package Privileges (Root Package):

    ![](/img/2019-07-01-15-33-25.png)


## Creación de servicios XSJS en HANA (1)
### Servicio XSJS que retorna texto
1.	Entrar al HANA editor
2.	Crear la jerarquía de paquetes /everis/test/julio2019/
3.	Crear aplicación

    ![](/img/2019-07-01-15-35-01.png)
    ![](/img/2019-07-01-15-35-05.png)

4.	Crear el archivo `/everis/test/julio2019/services/textService.xsjs`

    ```javascript
    $.response.contentType="text/html";
    $.response.setBody("My first service");
    ```

5.	Ejecutar el servicio:<br>
https://\<host\>.hanatrial.ondemand.com/everis/test/julio2019/services/textService.xsjs

6.	También se puede hacer desde Postman

### Servicio XSJS que retorna JSON
1.	Crear el archivo `/everis/test/julio2019/services/jsonService.xsjs`
    ```javascript
    var output = {
      "everis": "string",
      "car": true,
      "ses": 2,
      "others": false
    };

    $.response.contentType = "application/json";
    $.response.setBody(JSON.stringify(output));
    $.response.status = $.net.http.OK;
    ```

2.	Ejecutar el servicio:<br>
https://\<host\>.hanatrial.ondemand.com/everis/test/julio2019/services/jsonService.xsjs

## Creación de Tablas en HANA
### Crear schema
1.	Crear archivo `/everis/test/julio2019/data/projects.hdbschema`

    ```javascript
    schema_name = "projects";
    ```

### Crear database definition
1.	Crear archivo `/everis/test/julio2019/data/projectsdb.hdbdd`

    ```javascript
    namespace everis.test.julio2019.data;

    @Schema: 'projects'

    context projectsdb {
      type SDate : UTCTimestamp; 
      type SString : String(40);
      type LString : String(255);

      @Catalog.tableType : #COLUMN
      entity Project {
        key Id: Integer;
            ProjectName: SString;
            ProjectType: LString;
            StartDate: SDate;
            IsInternal: Integer;
        };
    }; 
    ```

2.	Asignar al usuario desarrollador el siguiente object privilege:<br>
  ![](/img/2019-07-16-00-06-26.png)

3.	Acceder al HANA Catalog para visualizar la tabla que creamos:
https://\<host\>.hanatrial.ondemand.com/sap/hana/ide/catalog/


### Cargar datos de prueba
1.	Crear archivo `/everis/test/julio2019/data/sample_Project.csv
    ```
    1,eMOC,Traditional,2019-01-01,0
    2,Drizzle,Agile,2019-02-01,1
    3,Impl.S/4HANA Laive,Traditional,2019-03-01,0
    ```

2.	Crear archivo `/everis/test/julio2019/data/projectsdb-Project.hdbti`

    ```javascript
    import = 
        [{
            cdstable  =	"everis.test.julio2019.data::projectsdb.Project";
            file = "everis.test.julio2019.data:sample_Project.csv"; 	     
            header = false;		
        }];
    ```

3.	Visualizar data de prueba en el HANA Catalog.

## Creación de servicios XSJS en HANA (2)
### Lectura de tabla - Resultado como texto
1.	Crear archivo `/everis/test/julio2019/services/getProjectDataAsText.xsjs`:
    ```javascript
    $.response.contentType = "text/html";
    var output = "Everis SAP Innovation!<br><br>";

    //Open a database connection
    var conn = $.db.getConnection();

    //Prepare a simple SQL statement
    var pstmt = conn.prepareStatement('SELECT * FROM "projects"."everis.test.julio2019.data::projectsdb.Project"');

    //Execute the query
    var rs = pstmt.executeQuery();

    //Check the query result
    output = output + "This is the response from my SQL:<br><br>";
    while (rs.next()) {
      //Something went wrong: Return an error
      output = output + rs.getString(1) + ' ' + rs.getString(2) + ' ' + rs.getString(3) + ' ' + rs.getString(4) + '<br>';
    }
      
    //Close the database connection
    rs.close();
    pstmt.close();
    conn.close();

    //Return the HTML response.
    $.response.setBody(output);
    ```

### Lectura de tabla - Resultado como JSON
1.	Crear archivo `/everis/test/julio2019/services/getProjectDataAsJson.xsjs`:
    ```javascript
    var jsonOutput = [];

    //Open a database connection
    var conn = $.db.getConnection();

    //Prepare a simple SQL statement
    var pstmt = conn.prepareStatement('SELECT * FROM "projects"."everis.test.julio2019.data::projectsdb.Project"');

    //Execute the query
    var rs = pstmt.executeQuery();

    //Check the query result
    while (rs.next()) {
      jsonOutput.push({
        "Name": rs.getString(2),
        "Type": rs.getString(3),
        "Date": rs.getString(4),
        "IsInternal": rs.getString(5)
      });
    }

    //Close the database connection
    rs.close();
    pstmt.close();
    conn.close();

    //Return the JSON response
    $.response.contentType = "application/json";
    $.response.setBody(JSON.stringify(jsonOutput));
    ```

### Utilizar Sequences
1. Para crear una secuencia, utilizamos el archivo `.hdbsequence`:
    ```
    schema= "projects";
    start_with=1;
    nomaxvalue=true;
    minvalue=1;
    increment_by=1;
    depends_on_table="everis.test.julio2019.data::projectsdb.Project";
    ```

2. Para obtener su valor, se ejecuta la siguiente sentencia SQL:
    ```SQL
    SELECT "projects"."everis.test.julio2019.data::Project".NEXTVAL FROM dummy;
    ```
3. Para reiniciar el valor de la secuencia:
    ```SQL
    ALTER SEQUENCE "projects"."everis.test.julio2019.data::Project" RESTART WITH 1;
    ```
    
## Debugging en HANA

1. Agregar el rol `sap.hana.xs.ide.roles::CatalogDeveloper` al usuario SYSTEM.
2. Para debuggear, ejecutar con el usuario SYSTEM la siguiente sentencia (omitir algún error que señale el editor):
   
   ```sql
   alter system alter configuration ('xsengine.ini','SYSTEM') set ('debugger','enabled')='true' with reconfigure;
   ```

3. Asignar el rol `sap.hana.xs.debugger::Debugger` al usuario desarrollador:

   ![](/img/2019-07-02-23-18-04.png)
   

4. Refrescar el Editor, y setear algún Breakpoint:
  
    ![](/img/2019-07-02-22-56-00.png)

5. Al ejecutar el servicio, se abrirá el debug:
   
    ![](/img/2019-07-02-22-56-21.png)

## SAP HANA XS Data Services (XSDS)
Comencemos un nuevo modelo de BD:<br>
*Schema (`ventas.hdbschema`):*
```javascript
schema_name = "ventas";
```

*CDS Document (`ventasdb.hdbdd`):*
```javascript
namespace everis.test.julio2019.ventas;

@Schema: 'ventas'
context ventasdb {

    Entity OrdenCompra {
        key IdOrdenCompra: Integer;
        Campo1: String(100);
        Items: Association [0..*] to Item on Items.IdOrdenCompra2=IdOrdenCompra;
    }
    
    Entity Item {
        key IdOrdenCompra2: Integer;
        key IdItem: Integer;
        ToHeader: Association [1] to OrdenCompra on ToHeader.IdOrdenCompra=IdOrdenCompra2;
    }
} 
```

***Nota:** Recordar asignar el Object Privilege relacionado al schema nuevo `ventas` que se está creando.*

### Importar la librería
1. Para poder utilizar la librería `xsds` se debe importar la librería:
    ```javascript
    $.import("sap.hana.xs.libs.dbutils", "xsds");

    var xsds = $.sap.hana.xs.libs.dbutils.xsds;
    ```

### Lectura de registros para Unmanaged Associations
1. Importar las entidades y usar el método `$select` para filtrar registros.
    ```javascript
    $.import("sap.hana.xs.libs.dbutils", "xsds");

    var xsds = $.sap.hana.xs.libs.dbutils.xsds; // XS Data Services

    var OC = xsds.$importEntity("everis.test.julio2019.ventas", "ventasdb.OrdenCompra");

    var ordenes = OC.$select({
      IdOrdenCompra: 2
    });

    $.response.contentType = "application/json";
    $.response.setBody(JSON.stringify(ordenes));
    ```

### Lectura de registros para Managed Associations
1. Importar las entidades y usar el método `$get` para obtener un registro. Luego, será necesario usar el método `$clone` para poder pasar a objeto JSON, la instancia retornada por `$get`.
    ```javascript
    $.import("sap.hana.xs.libs.dbutils", "xsds");

    var xsds = $.sap.hana.xs.libs.dbutils.xsds; // XS Data Services

    var OC = xsds.$importEntity("everis.test.julio2019.ventas", "ventasdb.OrdenCompra");

    var ordenCompra1 = OC.$get({
      IdOrdenCompra: 2
    });

    var ordenCompraJson = ordenCompra1.$clone();
    $.response.contentType = "application/json";
    $.response.setBody(JSON.stringify(ordenCompraJson));
    ```

2. Importar las entidades y usar el método `$findAll` para obtener los registros. Luego, será necesario usar el método `$clone` para poder pasar a objetos JSON, la instancias retornadas por `$findAll`.
    ```javascript
    $.import("sap.hana.xs.libs.dbutils", "xsds");

    var xsds = $.sap.hana.xs.libs.dbutils.xsds; // XS Data Services

    var OC = xsds.$importEntity("everis.test.julio2019.ventas", "ventasdb.OrdenCompra");

    var ordenes = OC.$findAll({});

    var ordenesJson = ordenes.map(function(orden) {
      return orden.$clone();
    });

    $.response.contentType = "application/json";
    $.response.setBody(JSON.stringify(ordenesJson));
    ```

## SAP HANA XS Procedures
1. Crear un Table Type con SQL (en el Catálogo):
    ```SQL
    CREATE TYPE tt_ordencompra AS TABLE (
      IdOrdenCompra INTEGER,
      Campo1 VARCHAR(100));
    ```

2. Crear un Procedure en el archivo `procedure1.hdbprocedure`:
    ```SQL
    PROCEDURE "ventas"."everis.test.julio2019.ventas::procedure1" ( IN modo INT, OUT output1 INT)--OUT output1 "ventas"."TT_ORDENCOMPRA")
      LANGUAGE SQLSCRIPT
      SQL SECURITY INVOKER
      READS SQL DATA AS
    BEGIN
      /*************************************
          Write your procedure logic 
      *************************************/
      IF :modo = 1 THEN 
            output1 =  1;--SELECT "IdOrdenCompra" AS "IDORDENCOMPRA", "Campo1" AS "CAMPO1" FROM "ventas"."everis.test.julio2019.ventas::ventasdb.OrdenCompra";
        ELSEIF :modo = 2 THEN
            output1 = 2;--SELECT "IdOrdenCompra" AS "IDORDENCOMPRA" FROM "ventas"."everis.test.julio2019.ventas::ventasdb.OrdenCompra";
        END IF;
    END
    ```

### Llamar un Procedure desde un servicio .xsjs

1. Para esto se usa la librería `procedures`:
    ```javascript
    var XSProc = $.import("sap.hana.xs.libs.dbutils", "procedures"); // import the library
    var proc1 = XSProc.allProcedures("ventas", "everis.test.julio2019.ventas").procedure1;

    var result = proc1(1); // call the procedure

    $.response.contentType = "application/json";
    $.response.setBody(JSON.stringify(result));
    ```

## OData en HANA XS
### Creación de un servicio OData en HANA XS

1. Crear el archivo `/everis/test/julio2019/services/Project.xsodata`:
    ```javascript
    service {
        "ventas"."everis.test.julio2019.ventas::ventasdb.OrdenCompra" as "OrdenCompra" navigates ("OCItem" as "Items");

        "ventas"."everis.test.julio2019.ventas::ventasdb.Item" as "Item";

        association "OCItem" with referential constraint principal "OrdenCompra"("IdOrdenCompra") multiplicity "1" dependent "Item"("IdOrdenCompra2") multiplicity "*"; 
    } 
    ```

    **Nota:** Para poder leer los datos de la tabla mediante el servicio OData, es necesario agregar algunos roles. 

### Extender/ampliar una operación de servicio OData en HANA XS
Se puede ampliar o reemplazar la funcionalidad antes/después de una operación Create, Update o Delete de una Entidad OData. (No es posible hacer esto con GET)

1. Definir la ampliación en el archivo `.xsodata`. Por ejemplo, se define una ampliación que se ejecutará antes de la operación *update*:
    ```javascript
    "ventas"."everis.test.julio2019.ventas::ventasdb.OrdenCompra" 
      as "OrdenCompra" navigates ("OCItem" as "Items")
      update events (before "everis.test.julio2019.ventas:jsexit.xsjslib::before_update");
    ```
2. En un archivo `jsexit.xsjslib` (al que se hace referencia en el `.xsodata`) definir la función especificada:
    ```javascript
    function before_update (param) { 
      // Se genera una tabla temporal (afterTableName), la cual tiene 1 sólo registro (el que se envía en el body de la petición)
      var after = param.afterTableName, 
          stmt = 'select * from "'+ after + '"',  
          pStmt = param.connection.prepareStatement( stmt ),  
          xStmt = pStmt.executeQuery();
        
      xStmt.next();
      var idOrdenCompra = xStmt.getString(1);
      var campo1 = xStmt.getString(2);

      if ("<valicion>") {
        // ...
      } else {
        return { HTTP_STATUS_CODE: 400, ERROR_MESSAGE: '...', DETAILS: '...'};
      }
    }
    ```

### Usar el OData Explorer

1. Dar click derecho en el archivo .xsodata y seleccionar la opción "Open OData Explorer":<br>
   ![](/img/2019-07-02-00-16-26.png)

# OData
## Parámetros OData

1. Ir a Postman e introducir el URL del servicio OData.
2. Se pueden probar distintos parámetros como $format, $filter, $select, $orderby
   
   Por ejemplo:<br>
   *https://\<host\>.hanatrial.ondemand.com/everis/test/julio2019/services/Project.xsodata/Project?\$format=json&\$filter=Id eq 1&\$select=Id,ProjectName,IsInternal*

3. Notar que OData trabaja sobre HTTP, por o que utiliza los mismos métodos (GET, POST, PUT, DELETE, MERGE).
4. OData tiene las siguientes operaciones:
* **Read:** Lectura de 1 registro.
* **Query:** Lecture de varios registros.
* **Create:** Creación de un nuevo registro.
* **Update:** Actualización de un registro existente.
* **Delete:** Borrado de un registro.

# SAP Cloud Platform Workflow

## Pre-requisitos para usar SCP Workflow
1. Activar servicio Portal
2. Activar servicio Web IDE
3. Activar servicio Workflow

## Activar la Extensión de Workflow en SAP Web IDE
1. Ir a Preferences
2. Ir a Extensions
3. Buscar la extensión de "Workflow"
4. Activarla y darle a "Save"

## Creación de un nuevo Workflow
1. En el Web IDE, crear un proyecto
   `File > New > Project from Template`
2. Seleccionar `All categories` en el filtro de Category.
3. Escoger el template de `Workflow Project`.
4. Colocar un nombre de proyecto.
5. Colocar un nombre del workflow.
6. Finish.

## Usando los Eventos, Tasks y Gateways

Para familiarizarnos con los distintos objetos que se pueden incluir en un Workflow, modelaremos un pequeño workflow sobre el siguiente caso (simplificado por cuestiones prácticas):

En el equipo de Innovación SAP hay 10 consultores SAP Cloud Platform, un Líder de Equipo llamado Christian A. y una Manager de Innovación llamada Inés.
El Líder puede **solicitar** un aumento de sueldo para alguno de los consultores de su equipo. En esta solicitud, incluirá el nombre del consultor, su código de empleado, un sueldo propuesto y un comentario con el sustento de la petición.<br>
Luego, la Manager recibirá esta solicitud en su bandeja, la revisará y podrá escoger entre aceptarla y rechazarla. **Si la rechaza**, le llegará al Líder una notificación en su bandeja de que su solicitud fue rechazada, y podrá reenviarla modificando los datos de la solicitud.
**Si la aprueba**, el flujo terminará.<br>

### Planteando la solución
El primer paso sería identificar cuándo y desde dónde se gatillará el workflow.
- El workflow se gatillará cuando el Líder envíe la solicitud de aumento.
- Se creará una aplicación de tipo Formulario con un botón `Solicitar Aumento`, el cual al ser presionado gatillará el Workflow.

Luego, identificamos qué tareas se deben modelar.
- A grandes rasgos, deberían existir estas tareas:
  - Solicitud de Aumento.
  - Aprobación de Aumento.
  - Corrección de Solicitud.

Adicionalmente, se puede obsevar que luego de la *Aprobación de Aumento* se deberá distinguir si la Manager la aprobó o rechazó.

### Modelando el workflow
1. En el Editor Visual de Workflow, incluir los siguientes elementos:
  - Evento Inicio
  - Evento Fin
  - User Task de *Aprobación de Aumento*<br>
    - Name: Aprobación de Aumento
    - Subject: Aprobación de Aumento
    - Users: `<S-User, Usuario de Manager>`
    - Type: Form
    - File Name: `FormularioAprobacion.form`
  - User Task de *Corrección de Solicitud*<br>
    - Name: Corrección de Solicitud
    - Subject: Corrección de Solicitud
    - Users: `<S-User, Usuario de Líder>`
    - Type: Form
    - File Name: `FormularioCorreccion.form`
  - Exclusive Gateway<br>
    - Enlace a User Task de *Corrección de Solicitud*:<br>
      - Name: No
      - Condition: `${usertasks.usertask3.last.decision=="rechazar_solicitud"}`. *Recordar que "usertask3" es el ID de la tarea, por lo que puede variar.*
    - Enlace a Evento *Fin*:<br>
      - Name: Si
      - Condition: Default
  
    ![](/img/2019-07-08-11-58-22.png)

## Creando los formularios
1. Click derecho a la raíz del proyecto, y dar en `New > Form`.
2. Ingresar el nombre del formulario, un id y una versión.<br>
  2.1 En la pestaña *Fields* se agregan los campos de formulario:<br>
      ![](/img/2019-07-08-12-01-15.png)
      En la pestaña *Decisions* se agregan los botones:<br>
      ![](/img/2019-07-08-12-02-01.png)<br><br>
  2.2 En la pestaña *Fields* se agregan los campos de formulario:<br>
      ![](/img/2019-07-08-12-15-47.png)
      En la pestaña *Decisions* se agregan los botones:<br>
      ![](/img/2019-07-08-12-16-00.png)

## Desplegando los elementos Workflow
Para probar un flujo de Workflow, se deben desplegar los siguientes objetos de forma **independiente**:
- Workflow<br>
  ![](/img/2019-07-08-12-20-25.png)
- Formularios (también uno por uno)<br>
  ![](/img/2019-07-08-12-21-38.png)

## Creando la aplicación SAPUI5 (Gatilla el Workflow)
1. Crear una aplicación nueva en base al template SAPUI5 Application.
     - Colocar como namespace `com.everis.julio2019`.
     - Nombre de la app `SolicitudAumento`.
2. Configurar una ruta en el archivo `neo-app.json` que apunte al destino `bpmworkflowruntime`:
    ```javascript
    "routes": [{
        // ...
        }, {
        "path": "bpmworkflowruntime", // Se usa en el código SAPUI5
        "target": {
          "type": "destination", // Tipo de ruta
          "name": "bpmworkflowruntime", // Nombre del destination
          "entryPath": "/workflow-service" // Ruta fija del servicio
        },
        "description": "Workflow API"
      }]
    ```

3. En la vista `SolicitudAumento.view.xml` crear un pequeño formulario:
    ```xml
    <mvc:View controllerName="com.everis.tutorial2019.SolicitudAumento.controller.SolicitudAumento" xmlns:mvc="sap.ui.core.mvc"
      displayBlock="true" xmlns="sap.m" xmlns:f="sap.ui.layout.form">
      <Shell id="shell">
        <App id="app">
          <pages>
            <Page id="page" title="{i18n>title}">
              <content>
                <Text text="{/variable}" maxLines="0" id="__text0"/>
                <f:SimpleForm editable="true" title="Ingrese datos" layout="ResponsiveGridLayout" labelSpanXL="3" labelSpanL="3" labelSpanM="3"
                  labelSpanS="12" adjustLabelSpan="false" emptySpanXL="4" emptySpanL="4" emptySpanM="4" emptySpanS="0" columnsXL="1" columnsL="1" columnsM="1"
                  singleContainerFullSize="false">
                  <f:content>
                    <Label text="{i18n>nombre}" required="true"></Label>
                    <Input id="nombreInput" value="{/variable}"></Input>
                    <Label text="{i18n>codigoEmpleado}"></Label>
                    <Input id="codigoEmpleadoInput"></Input>
                    <Label text="{i18n>sueldoPropuesto}"></Label>
                    <Input id="sueldoPropuestoInput" type="Number" placeholder="Ingrese el sueldo propuesto"></Input>
                    <Label text="{i18n>comentario}"></Label>
                    <TextArea id="comentarioTextArea"></TextArea>
                  </f:content>
                </f:SimpleForm>
              </content>
              <footer>
                <Toolbar>
                  <ToolbarSpacer/>
                  <Button text="{i18n>solicitarAumento}" press="onSolicitarAumento" type="Accept"/>
                </Toolbar>
              </footer>
            </Page>
          </pages>
        </App>
      </Shell>
    </mvc:View>
    ```
4. En el controlador `SolicitudAumento.controller.js`:
    ```javascript
    sap.ui.define([
      "sap/ui/core/mvc/Controller",
      "sap/m/MessageBox"
    ], function (Controller, MessageBox, JSONModel) {
      "use strict";

      return Controller.extend("com.everis.tutorial2019.SolicitudAumento.controller.SolicitudAumento", {
        onInit: function () {
          this.oView = this.getView();
        },

        _byId: function (sName) {
          var cmp = this.byId(sName);
          if (!cmp) {
            cmp = sap.ui.getCore().byId(sName);
          }
          return cmp;
        },

        onSolicitarAumento: function (oEvent) {
          var sNombre = this._byId("nombreInput").getValue();
          var sCodigoEmpleado = this._byId("codigoEmpleadoInput").getValue();
          var sSueldoPropuesto = this._byId("sueldoPropuestoInput").getValue();
          var sComentario = this._byId("comentarioTextArea").getValue();

          // Construir contexto
          var sNewWorkflowInstanceData = JSON.stringify({
            definitionId: "workflow1",
            context: {
              solicitud: {
                nombre: sNombre,
                codigoEmpleado: sCodigoEmpleado,
                sueldoPropuesto: parseFloat(sSueldoPropuesto),
                comentario: sComentario
              }
            }
          });

          // Instanciar workflow
          this.getWorkflowApiToken().then(function (sToken) {
            return this.createWorkflowInstance(sToken, sNewWorkflowInstanceData);
          }.bind(this)).then(function () {
            MessageBox.success("Solicitud de Aumento enviada correctamente");
          }).catch(function (sError) {
            MessageBox.error(sError);
          });
        },

        getWorkflowApiToken: function () {
          return new Promise(function (resolve, reject) {
            $.ajax({
              type: "GET",
              url: "/bpmworkflowruntime/rest/v1/xsrf-token",
              headers: {
                "X-CSRF-Token": "Fetch"
              },
              success: function (data, statusText, xhr) {
                var sToken = xhr.getResponseHeader("X-CSRF-Token");
                resolve(sToken);
              },
              error: function (errMsg) {
                reject(errMsg.statusText);
              },
              contentType: "application/json"
            });
          });
        },

        createWorkflowInstance: function (sToken, sContextData) {
          return new Promise(function (resolve, reject) {
            $.ajax({
              type: "POST",
              url: "/bpmworkflowruntime/rest/v1/workflow-instances",
              data: sContextData,
              headers: {
                "X-CSRF-Token": sToken
              },
              success: function () {
                resolve();
              },
              error: function (errMsg) {
                reject(errMsg.responseJSON.error.message);
              },
              dataType: "json",
              contentType: "application/json"
            });
          });
        }
      });
    });
    ```
5. En el archivo `i18n.properties` colocar la traducción de los textos:
    ```properties
    title=Solicitud de Aumento
    appTitle=Solicitud de Aumento
    appDescription=App Description

    nombre=Nombre
    codigoEmpleado=Codigo de Empleado
    sueldoPropuesto=Sueldo Propuesto
    comentario=Comentario
    solicitarAumento=Solicitar Aumento
    ```
## Desplegando y Registrando la aplicación en el Fiori Launchpad
1. Hacer click derecho sobre la raíz del proyecto SAPUI5.
2. Desplegar la aplicación en SAP Cloud Platform.<br>
    ![](/img/2019-07-08-19-45-01.png)
3. Registrar la aplicación en el Fiori Launchpad (opción que está debajo de "Deploy to SCP").
4. Indicar una descripción.
5. Marcar la opción de *Semantic Object*.
6. Indicar un Título, subtítulo y un icono. Estos últimos se pueden encontrar en la página [SAP Icons](https://sapui5.hana.ondemand.com/sdk/test-resources/sap/m/demokit/iconExplorer/webapp/index.html#/overview/SAP-icons).
7. Seleccionar un Catálogo y un Grupo.
8. Finish.

# Portal Service

# OData en ABAP

</div>