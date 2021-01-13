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
description: 'Resumen: obtenga información sobre cómo asociar grupos de servidores front-end con un almacén de supervisión usado por Skype Empresarial Server.'
ms.openlocfilehash: 4ec48e99da9a827cdc40d87c42ec764bda66a416
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830550"
---
# <a name="associate-a-monitoring-store-with-a-front-end-pool-in-skype-for-business-server"></a>Asociar un almacén de supervisión con un grupo de servidores front-end en Skype Empresarial Server 
**Resumen:** Obtenga información sobre cómo asociar grupos de servidores front-end con un almacén de supervisión usado por Skype Empresarial Server.
  
En Skype Empresarial Server, los datos de supervisión solo se pueden recopilar en grupos de servidores front-end que se han asociado a un almacén de supervisión, tarea que normalmente se lleva a cabo cuando se define un grupo de servidores front-end en el Generador de topologías.
  
## <a name="associate-a-monitoring-store-with-a-front-end-pool"></a>Asociar un almacén de supervisión con un grupo de servidores front-end

 Para asociar un almacén de supervisión con un nuevo grupo de servidores front-end, asegúrese de seleccionar  la opción Supervisión (registro detallado de llamadas y registro de métricas de calidad de la **experiencia)** en la página Seleccionar características del Asistente para definir nuevo grupo de servidores front-end. Ten en cuenta que, si seleccionas esta opción, también debes especificar un SQL para completar el asistente; sin embargo, este almacén no tiene que existir en el momento de ejecutar el asistente. Esto significa que primero puede asociar un grupo de servidores con un almacén de supervisión y, a continuación, configurarlo y configurarlo posteriormente.
  
O bien, asocie un grupo de servidores front-end ya existente a un almacén de supervisión nuevo o diferente ejecutando el procedimiento siguiente:
  
1. Haga **clic en** Inicio, en **Todos** los programas, en Skype Empresarial **Server 2015** y, a continuación, en Generador de topologías de Skype Empresarial **Server.**
    
2. En el cuadro de diálogo **Generador de topologías**, seleccione **Descargar topología de la implementación existente** y después haga clic en **Aceptar**.
    
3. En el cuadro de diálogo **Guardar como**, escriba un nombre de archivo para la topología actual y después haga clic en **Guardar**. Más tarde, si tiene problemas con la nueva topología, podrá recuperar y volver a publicar la topología guardada.
    
4. En el Generador de topologías, expanda Skype Empresarial **Server,** expanda el nombre del sitio que contiene el grupo de servidores front-end y, a continuación, haga clic en Expandir grupos de servidores **front-end Enterprise Edition.**
    
5. Haga clic con el botón secundario en el nombre del grupo de servidores que se asociará al almacén de supervisión y después haga clic en **Editar propiedades**.
    
6. En el cuadro de diálogo **Editar propiedades**, en la pestaña **General**, seleccione la opción **Supervisión (métricas CDR y QoE)** y después seleccione una base de datos SQL Server ya existente en la lista desplegable **Supervisión de SQL Server Store**. (O bien, haga clic en **Nuevo** para asociar el grupo de servidores a un almacén de base de datos nuevo). Si decide usar un almacén de base de datos nuevo, en el cuadro de diálogo **Definir nuevo almacén SQL**, escriba el nombre de dominio completo del equipo de SQL Server en el cuadro **FQDN de SQL Server**. Si quiere usar la instancia de SQL Server habitual del almacén, seleccione **Instancia predeterminada**, si no, seleccione **Instancia con nombre** y escriba el nombre de la instancia en el cuadro **Instancia con nombre**.
    
    El cuadro de diálogo **Editar propiedades** también le da la opción de crear un reflejo de SQL para la base de datos de supervisión (un reflejo de SQL permite mantener dos copias de las bases de datos de supervisión, una copia almacenada en el PC del almacén de supervisión y otra en el PC del reflejo de SQL). Para habilitar la creación de reflejos, seleccione T su instancia **SQL** está en relación de reflejo y escriba el número de puerto para el servidor reflejado en el cuadro Número de puerto de creación **de** reflejos.
    
7. En el cuadro de diálogo **Editar propiedades**, haga clic en **Aceptar**.
    
Después de asociar el almacén de supervisión al grupo de servidores front-end, publique la nueva topología antes de que los cambios entren en vigor. Para publicar la nueva topología, ejecute los pasos siguientes en el Generador de topologías:
  
1. Haga clic en **Acción**, seleccione **Topología** y haga clic en **Publicar**.
    
2. En el Asistente para publicar topología, en la página **Publicar la topología**, haga clic en **Siguiente**.
    
3. En la página **Asistente de publicación completado**, haga clic en **Finalizar**.
    
Después de publicar la topología, instale la base de datos de supervisión en el PC que hospedará el almacén de supervisión. La base de datos de supervisión se puede instalar mediante el Shell de administración de Skype Empresarial Server y Windows PowerShell. Para instalar la base de datos localmente (es decir, para instalar la base de datos en el mismo equipo donde se ejecuta el Shell de administración de Skype Empresarial Server), inicie el Shell de administración en el equipo adecuado, escriba el siguiente comando y presione ENTRAR:
  
```powershell
Install-CsDatabase -LocalDatabases
```

Al ejecutar el comando anterior, Install-CsDatabase leerá la topología actual de Skype Empresarial Server, determinará qué bases de datos deben instalarse en el equipo local y, a continuación, instalará y configurará automáticamente cada una de esas bases de datos.
  
Para instalar la base de datos en un PC remoto (es decir, en un PC que no sea el PC en el que se ejecute el shell de administración), incluya al menos dos parámetros: el parámetro ConfiguredDatabases y el parámetro SqlServerFqdn. Estos parámetros le piden al cmdlet Install-CsDatabase que recupere la topología de Skype Empresarial Server y, a continuación, instale y configure las bases de datos necesarias en el equipo especificado por el parámetro SqlServerFqdn. El parámetro SqlServerFqdn debe usar un valor que represente el nombre de dominio completo del PC donde se vayan a instalar las bases de datos.
  
Por ejemplo, este comando instala la base de datos de supervisión en el PC atl-sql-001.litwareinc.com:
  
```powershell
Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com
```

Como alternativa, puede instalar la base de datos de supervisión ejecutando el Asistente para la implementación de Skype Empresarial Server en el equipo que hospedará el almacén de supervisión. Para ello, inicie sesión en el PC pertinente y ejecute el procedimiento siguiente:
  
1. Haga **clic en Inicio,** **en Todos** los programas, en Skype Empresarial Server **2015** y, a continuación, en Asistente para la implementación **de Skype Empresarial Server.**
    
2. En el Asistente para la implementación, haga **clic en Instalar o actualizar el sistema de Skype Empresarial Server.**
    
3. En la **página Implementar,** en Paso **2:** Instalar o quitar componentes de Skype Empresarial Server, haga clic **en Ejecutar de nuevo.**
    
4. En el Asistente para configurar componentes de Skype Empresarial Server, en la página Configurar componentes de **Skype Empresarial Server,** haga clic **en Siguiente.**
    
5. En **la** página Especificar ruta de acceso a las API, escriba la ruta de acceso al archivo Ocscore.msi (un archivo incluido con los medios de instalación de Skype Empresarial Server) y, a continuación, haga clic en **Siguiente.**
    
6. En la página **Ejecución de comandos**, haga clic en **Finalizar**.
    
Para asegurarse de que se han iniciado todos los servicios necesarios de Skype Empresarial Server, haga clic en **Ejecutar** bajo el encabezado **Paso 4:** Iniciar servicios en la **página** Implementar
  

