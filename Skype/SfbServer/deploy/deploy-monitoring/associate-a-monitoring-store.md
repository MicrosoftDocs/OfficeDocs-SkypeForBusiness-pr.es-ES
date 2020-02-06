---
title: Asociar una tienda de supervisión con un grupo de servidores front-end en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
description: 'Resumen: Obtenga información sobre cómo asociar grupos de servidores front-end con un almacén de supervisión usado por Skype empresarial Server.'
ms.openlocfilehash: 26d846ad533c5ea49fa371cfa4fedab24bf56307
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790048"
---
# <a name="associate-a-monitoring-store-with-a-front-end-pool-in-skype-for-business-server"></a>Asociar una tienda de supervisión con un grupo de servidores front-end en Skype empresarial Server 
**Resumen:** Obtenga información sobre cómo asociar grupos de servidores front-end con una tienda de supervisión usada por Skype empresarial Server.
  
En Skype empresarial Server, los datos de supervisión solo se pueden recopilar en grupos front-end que se hayan asociado a una tienda de supervisión, una tarea que normalmente se lleva a cabo al definir un grupo de servidores front-end en el generador de topología.
  
## <a name="associate-a-monitoring-store-with-a-front-end-pool"></a>Asociar un almacén de supervisión a un grupo de servidores front-end

 Para asociar un almacén de supervisión a un grupo de servidores front-end nuevo, seleccione la opción **Supervisión (registros detallados de llamadas y registro de métrica de Calidad de la experiencia)** en la página **Seleccionar características** del Asistente para definir nuevo grupo de servidores front-end. Recuerde que si selecciona esta opción, también debe especificar un almacén SQL para completar el asistente. Ahora bien, no es obligatorio que este almacén exista en el momento que ejecute el asistente. Es decir, asocie primero un grupo de servidores a un almacén de supervisión y después instale y configure el almacén.
  
O bien, asocie un grupo de servidores front-end ya existente a un almacén de supervisión nuevo o diferente ejecutando el procedimiento siguiente:
  
1. Haga clic en **Inicio**, seleccione **todos los programas**, **Skype empresarial Server 2015**y, a continuación, haga clic en **generador de topologías de Skype empresarial Server**.
    
2. En el cuadro de diálogo **Generador de topologías**, seleccione **Descargar topología de la implementación existente** y después haga clic en **Aceptar**.
    
3. En el cuadro de diálogo **Guardar como**, escriba un nombre de archivo para la topología actual y después haga clic en **Guardar**. Más tarde, si tiene problemas con la nueva topología, podrá recuperar y volver a publicar la topología guardada.
    
4. En el generador de topologías, expanda **Skype empresarial Server**, expanda el nombre del sitio que contiene el grupo de servidores front-end y, a continuación, haga clic en expandir **agrupaciones front-end de Enterprise Edition**.
    
5. Haga clic con el botón secundario en el nombre del grupo de servidores que se asociará al almacén de supervisión y después haga clic en **Editar propiedades**.
    
6. En el cuadro de diálogo **Editar propiedades**, en la pestaña **General**, seleccione la opción **Supervisión (métricas CDR y QoE)** y después seleccione una base de datos SQL Server ya existente en la lista desplegable **Supervisión de SQL Server Store** (o bien haga clic en **Nuevo** para asociar el grupo de servidores a un almacén de base de datos nuevo). Si decide usar un almacén de base de datos nuevo, en el cuadro de diálogo **Definir nuevo almacén SQL**, escriba el nombre de dominio completo del equipo de SQL Server en el cuadro **FQDN de SQL Server**. Si quiere usar la instancia de SQL Server habitual del almacén, seleccione **Instancia predeterminada**, si no, seleccione **Instancia con nombre** y escriba el nombre de la instancia en el cuadro **Instancia con nombre**.
    
    El cuadro de diálogo **Editar propiedades** también le da la opción de crear un reflejo de SQL para la base de datos de supervisión (un reflejo de SQL permite mantener dos copias de las bases de datos de supervisión, una copia almacenada en el PC del almacén de supervisión y otra en el PC del reflejo de SQL). Para habilitar la creación de reflejos, seleccione la **instancia de SQL está en la relación de reflejo** e introduzca el número de puerto para el servidor reflejado en el cuadro **número de puerto de creación de reflejo** .
    
7. En el cuadro de diálogo **Editar propiedades**, haga clic en **Aceptar**.
    
Después de asociar el almacén de supervisión al grupo de servidores front-end, publique la nueva topología antes de que los cambios entren en vigor. Para publicar su nueva topología, siga los pasos que se indican en el generador de topología:
  
1. Haga clic en **Acción**, seleccione **Topología** y haga clic en **Publicar**.
    
2. En el Asistente para publicar topología, en la página **Publicar la topología**, haga clic en **Siguiente**.
    
3. En la página **Asistente para publicación completado**, haga clic en **Finalizar**.
    
Después de publicar la topología, instale la base de datos de supervisión en el equipo que hospedará el almacén de supervisión. La base de datos de supervisión se puede instalar mediante el shell de administración de Skype empresarial Server y Windows PowerShell. Para instalar la base de datos de forma local (es decir, para instalar la base de datos en el mismo equipo en el que se ejecuta el shell de administración de Skype empresarial Server), inicie el shell de administración en el equipo correspondiente, escriba el siguiente comando y presione ENTRAR:
  
```powershell
Install-CsDatabase -LocalDatabases
```

Al ejecutar el comando anterior, install-CsDatabase leerá la topología actual de Skype empresarial Server, determinará qué bases de datos deben instalarse en el equipo local y, a continuación, instalará y configurará automáticamente cada una de esas bases de datos.
  
Para instalar la base de datos en un equipo remoto (es decir, en un equipo que no sea el equipo en el que se ejecute el shell de administración), incluya al menos dos parámetros: el parámetro ConfiguredDatabases y el parámetro SqlServerFqdn. Estos parámetros indican al cmdlet install-CsDatabase para que recupere la topología de Skype empresarial Server y, a continuación, instale y configure las bases de datos necesarias en el equipo especificado por el parámetro SqlServerFqdn. El parámetro SqlServerFqdn necesita usar un valor que represente el nombre de dominio completo del equipo donde se vayan a instalar las bases de datos.
  
Por ejemplo, este comando instala la base de datos de supervisión en el PC atl-sql-001.litwareinc.com:
  
```powershell
Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com
```

Como alternativa, puede instalar la base de datos de supervisión ejecutando el Asistente para la implementación de Skype empresarial Server en el equipo que hospedará el almacén de supervisión. Para ello, inicie sesión en el equipo pertinente y ejecute el procedimiento siguiente:
  
1. Haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Skype empresarial Server 2015**y, a continuación, haga clic en **Asistente de implementación de Skype empresarial Server**.
    
2. En el Asistente para la implementación, haga clic en **instalar o actualizar el sistema de Skype empresarial Server**.
    
3. En la página **implementar** , en **paso 2: configurar o quitar componentes de Skype empresarial Server**, haga clic en **Ejecutar de nuevo**.
    
4. En el Asistente para la instalación de componentes de Skype empresarial Server, en la página **instalar componentes de Skype empresarial Server** , haga clic en **siguiente**.
    
5. En la página **especificar la ruta de acceso a los MSI** , escriba la ruta de acceso al archivo Ocscore. msi (un archivo incluido con los medios de instalación de Skype empresarial Server) y, a continuación, haga clic en **siguiente**.
    
6. En la página **Ejecutar comandos**, haga clic en **Finalizar**.
    
Para asegurarse de que todos los servicios de Skype empresarial necesarios se hayan iniciado, haga clic en **Ejecutar** en el encabezado **paso 4: iniciar servicios** en la página **implementar**
  

