---
title: Asociar un almacén de supervisión con un grupo de servidores front-end en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
description: 'Summary: Learn how to associate Front End pools with a monitoring store used by Skype Empresarial Server.'
ms.openlocfilehash: 92713d8b6940011c97507a7138e05e80e1d119b302f9f58843b90bb9861005e9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307801"
---
# <a name="associate-a-monitoring-store-with-a-front-end-pool-in-skype-for-business-server"></a>Asociar un almacén de supervisión con un grupo de servidores front-end en Skype Empresarial Server 
**Resumen:** Obtenga información sobre cómo asociar grupos de servidores front-end con un almacén de supervisión usado por Skype Empresarial Server.
  
En Skype Empresarial Server, los datos de supervisión solo se pueden recopilar en grupos de servidores front-end asociados con un almacén de supervisión, tarea que normalmente se lleva a cabo al definir un grupo de servidores front-end en el Generador de topologías.
  
## <a name="associate-a-monitoring-store-with-a-front-end-pool"></a>Asociar un almacén de supervisión con un grupo de servidores front-end

 Para asociar un almacén de supervisión con un nuevo grupo de servidores front-end, asegúrese de seleccionar la opción Supervisión (registro detallado de llamadas y registro de métricas de calidad de **experiencia)** en la página **Seleccionar** características del asistente Definir nuevo grupo de servidores front-end. Tenga en cuenta que, si selecciona esta opción, también debe especificar un almacén SQL para completar el asistente; sin embargo, este almacén no tiene que existir en el momento en que se ejecuta el asistente. Esto significa que primero puedes asociar un grupo de servidores a un almacén de supervisión y, a continuación, configurarlo y configurarlo posteriormente.
  
O bien, asocie un grupo de servidores front-end ya existente a un almacén de supervisión nuevo o diferente ejecutando el procedimiento siguiente:
  
1. Haga **clic en** Inicio , en **Todos** los programas, Skype Empresarial Server **2015** y, a continuación, haga clic **Skype Empresarial Server Generador de topologías**.
    
2. En el cuadro de diálogo **Generador de topologías**, seleccione **Descargar topología de la implementación existente** y después haga clic en **Aceptar**.
    
3. En el cuadro de diálogo **Guardar como**, escriba un nombre de archivo para la topología actual y después haga clic en **Guardar**. Más tarde, si tiene problemas con la nueva topología, podrá recuperar y volver a publicar la topología guardada.
    
4. En el Generador de topologías, **expanda Skype Empresarial Server**, expanda el nombre del sitio que contiene el grupo de servidores front-end y, a continuación, haga clic en expandir Enterprise Edition grupos de **servidores front-end**.
    
5. Haga clic con el botón secundario en el nombre del grupo de servidores que se asociará al almacén de supervisión y después haga clic en **Editar propiedades**.
    
6. En el cuadro de diálogo **Editar propiedades**, en la pestaña **General**, seleccione la opción **Supervisión (métricas CDR y QoE)** y después seleccione una base de datos SQL Server ya existente en la lista desplegable **Supervisión de SQL Server Store**. (O bien, haga clic en **Nuevo** para asociar el grupo de servidores a un almacén de base de datos nuevo). Si decide usar un almacén de base de datos nuevo, en el cuadro de diálogo **Definir nuevo almacén SQL**, escriba el nombre de dominio completo del equipo de SQL Server en el cuadro **FQDN de SQL Server**. Si quiere usar la instancia de SQL Server habitual del almacén, seleccione **Instancia predeterminada**, si no, seleccione **Instancia con nombre** y escriba el nombre de la instancia en el cuadro **Instancia con nombre**.
    
    El cuadro de diálogo **Editar propiedades** también le da la opción de crear un reflejo de SQL para la base de datos de supervisión (un reflejo de SQL permite mantener dos copias de las bases de datos de supervisión, una copia almacenada en el PC del almacén de supervisión y otra en el PC del reflejo de SQL). Para habilitar la creación de reflejos, seleccione T **su** SQL está en relación de creación de reflejo y escriba el número de puerto para el servidor reflejado en el cuadro Número de **puerto de creación de reflejo.**
    
7. En el cuadro de diálogo **Editar propiedades**, haga clic en **Aceptar**.
    
Después de asociar el almacén de supervisión al grupo de servidores front-end, publique la nueva topología antes de que los cambios entren en vigor. Para publicar la nueva topología, ejecute los pasos siguientes en el Generador de topologías:
  
1. Haga clic en **Acción**, seleccione **Topología** y haga clic en **Publicar**.
    
2. En el Asistente para publicar topología, en la página **Publicar la topología**, haga clic en **Siguiente**.
    
3. En la página **Asistente de publicación completado**, haga clic en **Finalizar**.
    
Después de publicar la topología, instale la base de datos de supervisión en el PC que hospedará el almacén de supervisión. La base de datos de supervisión se puede instalar mediante el Shell Skype Empresarial Server administración y Windows PowerShell. Para instalar la base de datos localmente (es decir, para instalar la base de datos en el mismo equipo donde se ejecuta el Shell de administración de Skype Empresarial Server), inicie el Shell de administración en el equipo adecuado, escriba el siguiente comando y presione ENTRAR:
  
```powershell
Install-CsDatabase -LocalDatabases
```

Al ejecutar el comando anterior, Install-CsDatabase leerá la topología de Skype Empresarial Server actual, determinará qué bases de datos deben instalarse en el equipo local y, a continuación, instalará y configurará automáticamente cada una de esas bases de datos.
  
Para instalar la base de datos en un PC remoto (es decir, en un PC que no sea el PC en el que se ejecute el shell de administración), incluya al menos dos parámetros: el parámetro ConfiguredDatabases y el parámetro SqlServerFqdn. Estos parámetros le dicen al cmdlet Install-CsDatabase que recupere la topología de Skype Empresarial Server y, a continuación, instale y configure las bases de datos necesarias en el equipo especificado por el parámetro SqlServerFqdn. El parámetro SqlServerFqdn debe usar un valor que represente el nombre de dominio completo del PC donde se vayan a instalar las bases de datos.
  
Por ejemplo, este comando instala la base de datos de supervisión en el PC atl-sql-001.litwareinc.com:
  
```powershell
Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com
```

Como alternativa, puede instalar la base de datos de supervisión ejecutando el Asistente para la implementación de Skype Empresarial Server en el equipo que hospedará el almacén de supervisión. Para ello, inicie sesión en el PC pertinente y ejecute el procedimiento siguiente:
  
1. Haga **clic en** Inicio , en **Todos** los programas, haga clic Skype Empresarial Server **2015** y, a continuación, haga clic **Skype Empresarial Server Asistente para implementación**.
    
2. En el Asistente para implementación, haga clic **en Instalar o actualizar Skype Empresarial Server System**.
    
3. En la **página Implementar,** en **Paso 2:** Configurar o quitar componentes Skype Empresarial Server , haga clic **en Ejecutar de nuevo**.
    
4. En el Asistente para Skype Empresarial Server configuración, en la página **Componentes** Skype Empresarial Server instalación, haga clic en **Siguiente**.
    
5. En la página Especificar ruta de acceso a las **MSIs,** escriba la ruta de acceso al archivo Ocscore.msi (un archivo incluido con el medio de instalación de Skype Empresarial Server) y, a continuación, haga clic en **Siguiente**.
    
6. En la página **Ejecución de comandos**, haga clic en **Finalizar**.
    
Para asegurarse de que se han iniciado todos los Skype Empresarial Server necesarios, haga clic en **Ejecutar** bajo el encabezado **Paso 4: Iniciar** servicios en la **página** Implementar
  

