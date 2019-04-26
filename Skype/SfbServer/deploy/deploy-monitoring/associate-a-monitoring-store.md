---
title: Asociar un almacén de supervisión a un grupo de servidores Front-End en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
description: 'Resumen: Obtenga información sobre cómo asociar grupos Front-End con un almacén de supervisión usado Skype para Business Server.'
ms.openlocfilehash: 1156883202218dd536926f44f40e6ba774b17cb7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225486"
---
# <a name="associate-a-monitoring-store-with-a-front-end-pool-in-skype-for-business-server"></a>Asociar un almacén de supervisión a un grupo de servidores Front-End en Skype para Business Server 
**Resumen:** Obtenga información sobre cómo asociar grupos Front-End con un almacén de supervisión usado Skype para Business Server.
  
En Skype para Business Server, datos de supervisión solo se pueden recopilar en grupos de servidores Front-End que se han asociado con un almacén de supervisión, una tarea normalmente realizada al definir un grupo de servidores Front-End en el generador de topología.
  
## <a name="associate-a-monitoring-store-with-a-front-end-pool"></a>Asociar un almacén de supervisión a un grupo de servidores front-end

 Para asociar un almacén de supervisión a un grupo de servidores front-end nuevo, seleccione la opción **Supervisión (registros detallados de llamadas y registro de métrica de Calidad de la experiencia)** en la página **Seleccionar características** del Asistente para definir nuevo grupo de servidores front-end. Recuerde que si selecciona esta opción, también debe especificar un almacén SQL para completar el asistente. Ahora bien, no es obligatorio que este almacén exista en el momento que ejecute el asistente. Es decir, asocie primero un grupo de servidores a un almacén de supervisión y después instale y configure el almacén.
  
O bien, asocie un grupo de servidores front-end ya existente a un almacén de supervisión nuevo o diferente ejecutando el procedimiento siguiente:
  
1. Haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para Business Server 2015**y, a continuación, haga clic en **Skype para Business Server Topology Builder**.
    
2. En el cuadro de diálogo **Generador de topologías**, seleccione **Descargar topología de la implementación existente** y después haga clic en **Aceptar**.
    
3. En el cuadro de diálogo **Guardar como**, escriba un nombre de archivo para la topología actual y después haga clic en **Guardar**. Más tarde, si tiene problemas con la nueva topología, podrá recuperar y volver a publicar la topología guardada.
    
4. En el generador, expanda **Skype para Business Server**, expanda el nombre del sitio que contiene el grupo de servidores Front-End, a continuación, haga clic en expandir **los grupos de servidores Front-End de Enterprise Edition**.
    
5. Haga clic con el botón secundario en el nombre del grupo de servidores que se asociará al almacén de supervisión y después haga clic en **Editar propiedades**.
    
6. En el cuadro de diálogo **Editar propiedades**, en la pestaña **General**, seleccione la opción **Supervisión (métricas CDR y QoE)** y después seleccione una base de datos SQL Server ya existente en la lista desplegable **Supervisión de SQL Server Store** (o bien haga clic en **Nuevo** para asociar el grupo de servidores a un almacén de base de datos nuevo). Si decide usar un almacén de base de datos nuevo, en el cuadro de diálogo **Definir nuevo almacén SQL**, escriba el nombre de dominio completo del equipo de SQL Server en el cuadro **FQDN de SQL Server**. Si quiere usar la instancia de SQL Server habitual del almacén, seleccione **Instancia predeterminada**, si no, seleccione **Instancia con nombre** y escriba el nombre de la instancia en el cuadro **Instancia con nombre**.
    
    El cuadro de diálogo **Editar propiedades** también le da la opción de crear un reflejo de SQL para la base de datos de supervisión (un reflejo de SQL permite mantener dos copias de las bases de datos de supervisión, una copia almacenada en el PC del almacén de supervisión y otra en el PC del reflejo de SQL). Para habilitar la creación de reflejo, seleccione T **su instancia de SQL está en relación de reflejo** y escriba el número de puerto para el servidor reflejado en el cuadro **número de puerto de la creación de reflejo** .
    
7. En el cuadro de diálogo **Editar propiedades**, haga clic en **Aceptar**.
    
Después de asociar el almacén de supervisión al grupo de servidores front-end, publique la nueva topología antes de que los cambios entren en vigor. Para publicar su topología nuevo, complete los siguientes pasos en el generador de topología:
  
1. Haga clic en **Acción**, seleccione **Topología** y haga clic en **Publicar**.
    
2. En el Asistente para publicar topología, en la página **Publicar la topología**, haga clic en **Siguiente**.
    
3. En la página **Asistente para publicación completado**, haga clic en **Finalizar**.
    
Después de publicar la topología, instale la base de datos de supervisión en el equipo que hospedará el almacén de supervisión. La base de datos de supervisión puede instalarse mediante la Skype para Windows PowerShell y el Shell de administración de servidor de negocio. Para instalar la base de datos localmente (es decir, para instalar la base de datos en el mismo equipo donde se ejecuta el Skype para Shell de administración de servidor empresarial), inicie la consola de administración en el equipo adecuado, a continuación, escriba el comando siguiente y presione ENTRAR:
  
```
Install-CsDatabase -LocalDatabases
```

Cuando se ejecuta el comando anterior, Install-CsDatabase va a leer la Skype actual de topología de servidores de negocio, determinar qué bases de datos deben instalarse en el equipo local y, a continuación, instalar y configurar automáticamente cada una de dichas bases de datos.
  
Para instalar la base de datos en un equipo remoto (es decir, en un equipo que no sea el equipo en el que se ejecute el shell de administración), incluya al menos dos parámetros: el parámetro ConfiguredDatabases y el parámetro SqlServerFqdn. Estos parámetros indican el cmdlet Install-CsDatabase para recuperar la Skype de topología de servidores de negocio y, a continuación, instalar y configurar las bases de datos necesarios en el equipo especificado por el parámetro SqlServerFqdn. El parámetro SqlServerFqdn necesita usar un valor que represente el nombre de dominio completo del equipo donde se vayan a instalar las bases de datos.
  
Por ejemplo, este comando instala la base de datos de supervisión en el PC atl-sql-001.litwareinc.com:
  
```
Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com
```

Como alternativa, puede instalar la base de datos de supervisión mediante la ejecución de la Skype para el Asistente para la implementación de Business Server en el equipo que hospedará el almacén de supervisión. Para ello, inicie sesión en el equipo pertinente y ejecute el procedimiento siguiente:
  
1. Haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para Business Server 2015**y, a continuación, haga clic en **Skype para el Asistente para la implementación de servidor de negocio**.
    
2. En el Asistente para la implementación, haga clic en **instalar o actualización de Skype para Business Server System**.
    
3. En la página **implementar** , bajo **paso 2: el programa de instalación o quitar Skype para los componentes de servidor empresariales**, haga clic en **Ejecutar de nuevo**.
    
4. En el Skype el programa de instalación para el Asistente para componentes de Business Server, en la página de **Skype el programa de instalación para los componentes de Business Server** , haga clic en **siguiente**.
    
5. En la página **especificar la ruta de acceso a archivos MSI** , escriba la ruta de acceso al archivo Ocscore.msi (un archivo incluido con su Skype para los medios de instalación de Business Server) y, a continuación, haga clic en **siguiente**.
    
6. En la página **Ejecutar comandos**, haga clic en **Finalizar**.
    
Para asegurarse de que se han iniciado todas la Skype necesario para servicios de Business Server, haga clic en **Ejecutar** , bajo el encabezado **paso 4: iniciar servicios** en la página **implementar**
  

