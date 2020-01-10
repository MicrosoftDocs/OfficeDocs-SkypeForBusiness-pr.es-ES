---
title: Actualizar a Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: 'Resumen: Obtenga información sobre cómo actualizar Lync Server 2013 a Skype empresarial Server 2015. Descargue una prueba gratuita de Skype empresarial Server 2015 en el centro de evaluación de Microsoft en https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server:.'
ms.openlocfilehash: d9ce950ead8b8a3a8857c53d421470a0e647ea23
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001880"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a>Upgrade to Skype for Business Server 2015
 
**Resumen:** Obtenga información sobre cómo actualizar Lync Server 2013 a Skype empresarial Server 2015. Descargue una prueba gratuita de Skype empresarial Server 2015 en el [centro de evaluación de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Use los procedimientos de este documento para actualizar Lync Server 2013 a Skype empresarial Server 2015 con el generador de topologías de Skype empresarial Server y la nueva característica de actualización local. Si quiere actualizar a partir de Lync Server 2010 o de Office Communications Server 2007 R2, consulte [planear la actualización a Skype empresarial server 2015](../plan-your-deployment/upgrade.md).

> [!NOTE]
> Las actualizaciones locales estaban disponibles en Skype empresarial Server 2015, pero ya no son compatibles con Skype empresarial Server 2019. Se admite la coexistencia en paralelo, consulte [migración a Skype empresarial Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) para obtener más información.
  
## <a name="upgrade-from-lync-server-2013"></a>Actualizar desde Lync Server 2013

La actualización de Lync Server 2013 a Skype empresarial Server 2015 implica la instalación del software necesario, el uso del generador de topologías de Skype empresarial Server para actualizar las bases de datos del grupo, y el uso de la actualización local de Skype empresarial Server en cada uno de los servidores asociados con el grupo. Para completar la actualización, siga los ocho pasos descritos en este tema.
  
### <a name="before-you-begin"></a>Antes de comenzar

- Revise [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).
    
- Revise [los requisitos del servidor para Skype empresarial server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- [Instale los requisitos previos para Skype empresarial Server 2015](install/install-prerequisites.md) .
    
- [Instale Skype empresarial Server 2015](install/install.md) .
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a>Paso 1: Instalar las herramientas de administrador y descargar la topología

1. Conéctese al equipo de la topología que no tiene instalado Lync OCSCore o cualquier otro componente de Lync instalado.
    
2. Desde el disco de instalación de Skype empresarial Server 2015, ejecute **setup. exe** desde **OCS_Volume \setup\amd64**. 
    
3. Haga clic en **Instalar**. 
    
4. Acepte el acuerdo de licencia.
    
5. En el asistente de implementación, haga clic en **Instalar herramientas de administrador** y siga todos los pasos indicados.
    
     ![Captura de pantalla del Asistente para la implementación con enlace a Instalar herramientas de administrador activado.](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. En la pantalla Inicio de Windows, abra el generador de topologías de Skype empresarial Server.
    
7. Haga clic en **Descargar topología desde implementación existente** y haga clic en **Siguiente**.
    
8. Introduzca un nombre para la topología y haga clic en **Guardar**.
    
9. Vaya a la ubicación donde ha guardado la topología y cree una copia de la misma.
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a>Paso 2: Actualizar y publicar la topología con el Generador de topologías

Antes de iniciar el proceso de actualización, todos los servicios deben estar ejecutándose para los grupos que tiene previsto actualizar. El objetivo es que los cambios en la topología se repliquen en las bases de datos locales de los servidores del grupo.
  
> [!IMPORTANT]
>  Guarde una copia del archivo con la topología antes de actualizar. Después de la actualización, no podrá degradar la topología. > si los servicios están en los mismos servidores que las bases de datos, como el servicio de chat persistente está en el mismo servidor que la base de datos de chat persistente, omita este paso y vaya al paso 4. Después de detener los servicios, ejecute la instalación de la actualización local en cada uno de los servidores para actualizar las bases de datos locales.
  
> [!NOTE]
> Si la topología tiene una base de datos back-end que se refleja, verá tanto la base de datos principal como la reflejada al **publicar la topología** con el Generador de topologías. Asegúrese de que todas las bases de datos se estén ejecutando en la principal y seleccione solo la principal, no el reflejo, cuando publique la topología, de lo contrario verá una advertencia después de publicarla.
  
Elija una de las siguientes opciones para actualizar y publicar una nueva topología con el generador de topología de Skype empresarial Server 2015. Cuando complete los pasos y haya publicado la topología actualizada, vaya al paso 3 de este tema.
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a>Opción 1: Actualizar un grupo front-end aislado y los almacenes de archivado y supervisión asociados

Si el grupo que está actualizando tiene una dependencia respecto a un almacén de archivado y supervisión, dicho almacén también se actualizará al realizar los pasos siguientes.
  
1. En el generador de topología, haga clic con el botón secundario en un grupo de servidores de Lync Server 2013, seleccione **actualizar a Skype empresarial server 2015**y siga los pasos. 
    
     ![Captura de pantalla del menú contextual con opción de actualización de Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. En el generador de topologías, haga clic en**topología de publicación** de **acciones** > o en**publicación**de**topología** > de **acción** > . 
    
     ![Captura de pantalla del menú Acción con la opción Publicar topología en Topology Builder.](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. Durante la publicación, elija instalar una base de datos en el almacén de archivado y supervisión.
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a>Opción 2: actualizar el grupo de servidores front-end sin actualizar los almacenes de archivado y supervisión

Si sigue los siguientes pasos, el archivado y la supervisión del grupo seleccionado quedarán deshabilitados. Tras la actualización, el grupo no tendrá almacén de archivado y supervisión.
  
1. En el generador de topologías, seleccione el grupo de servidores de Lync Server 2013 que desea actualizar.
    
2. Quite la dependencia de los almacenes de supervisión y archivado de 2013 de Lync Server. 
    
   - Ir a la **acción** > **Editar propiedades**.
    
   - Desmarque la casilla **Archivado**.
    
     ![Captura de pantalla de la casilla de verificación Archivado del cuadro de diálogo Editar propiedades.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - Desmarque la casilla **Supervisión**.
    
     ![Captura de pantalla del cuadro de diálogo Editar propiedades que en la que aparece la casilla de verificación Supervisión.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Haga clic con el botón derecho en el grupo de servidores de Lync Server 2013, seleccione **actualizar a Skype empresarial server 2015**y siga los pasos. 
    
     ![Captura de pantalla del menú contextual con opción de actualización de Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. En el generador de topologías, haga clic en**topología de publicación** de **acciones** > o en**publicación**de**topología** > de **acción** > . 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a>Opción 3: actualizar el grupo de servidores front-end y asociarlo a los nuevos almacenes de almacenamiento y supervisión de Skype empresarial Server 2015

Si sigue los pasos siguientes, se interrumpirá el archivado y supervisión en el almacén anterior y se iniciará en un nuevo almacén que haya creado. 
  
1. En el generador de topologías, seleccione el grupo de servidores de Lync Server 2013 que desea actualizar. 
    
2. Quite la dependencia de los almacenes de supervisión y archivado de 2013 de Lync Server. 
    
   - Ir a la **acción** > **Editar propiedades**.
    
   - Desmarque la casilla **Archivado**.
    
     ![Captura de pantalla de la casilla de verificación Archivado del cuadro de diálogo Editar propiedades.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - Desmarque la casilla **Supervisión**.
    
     ![Captura de pantalla del cuadro de diálogo Editar propiedades que en la que aparece la casilla de verificación Supervisión.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Haga clic con el botón derecho en el grupo de servidores de Lync Server 2013, seleccione **actualizar a Skype empresarial server 2015**y siga los pasos. 
    
     ![Captura de pantalla del menú contextual con opción de actualización de Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. Cree un nuevo almacén SQL para archivado. 
    
   - Seleccione las propiedades de la sección y de**Editar**la **acción** > . 
    
   -  Marque la casilla **Archivado**.
    
   - Haga clic en **Nuevo**.
    
     ![Captura de pantalla del cuadro de diálogo Editar propiedades en la que aparece el botón Nuevo bajo la sección de archivado.](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. Cree un nuevo almacén SQL para supervisión. 
    
   - Seleccione las propiedades de la sección y de**Editar**la **acción** > . 
    
   -  Marque la casilla **Supervisión**.
    
   - Haga clic en **Nuevo**.
    
     ![Captura de pantalla del cuadro de diálogo Editar propiedades en la que aparece el botón Nuevo bajo la sección de supervisión.](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. En el generador de topologías, haga clic en**topología de publicación** de **acciones** > o en**publicación**de**topología** > de **acción** > . 
    
7. Durante la publicación, elija instalar la base de datos en el nuevo almacén de archivado y supervisión.
    
### <a name="step-3-wait-for-replication"></a>Paso 3: Esperar la replicación

Espere un tiempo para que la topología actualizada se publique en todos los servidores del entorno.
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a>Paso 4: Detener todos los servicios en el grupo a actualizar

En cada servidor que atiende el grupo que va a actualizar, ejecute el siguiente cmdlet en PowerShell:
  
```powershell
Disable-CsComputer -Scorch
```

Le recomendamos que use Disable-CsComputer, ya que es posible que tenga que reiniciar el servidor durante el proceso de actualización local. Si usas STOP-CsWindowsService, es posible que algunos servicios se reinicien automáticamente después de un reinicio. Esto puede provocar errores en la actualización local.
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a>Paso 5: Actualizar grupos front-end y servidores de grupos que no son front-end

> [!NOTE]
>  Antes de la actualización, instale todos los requisitos previos necesarios para Skype empresarial Server 2015, que incluyen: > al menos 32 GB de espacio libre antes de intentar una actualización. Además, asegúrese de que la unidad es una unidad local fija, no está conectada por USB o FireWire. está formateado con el sistema de archivos NTFS, no está comprimido y no contiene un archivo de página. > PowerShell versión 6.2.9200.0 o posterior. > instalada la última actualización acumulativa de Lync Server 2013. > SQL Server 2012 SP1. > de los siguientes KB (se instala automáticamente si usa Microsoft Update): > Windows Server 2008 R2-[KB2533623](https://support.microsoft.com/kb/2533623) de windows Server 2012-[KB2858668](https://support.microsoft.com/kb/2858668)> Windows Server 2012 R2- [KB2982006](https://support.microsoft.com/kb/2982006)
  
Use la actualización local en cada servidor para actualizar el grupo de servidores front-end, el grupo perimetral, el servidor de mediación y el grupo de chats persistentes.
  
1. En cada servidor, ejecute **setup. exe** desde **OCS_Volume \setup\amd64** en los medios de instalación de Skype empresarial Server 2015.
    
2. Acepte el contrato de licencia y siga las indicaciones para la actualización local.
    
3. Repita estos pasos para cada servidor del grupo de servidores front-end y en cada servidor de grupo que no sea front-end.
    
> [!NOTE]
> Es posible que se le solicite que reinicie el servidor durante la actualización local. Es normal. Después de reiniciar, la actualización local continuará desde el punto en que se quedó. 
  
Cuando la actualización local se complete correctamente, verá el siguiente mensaje.
  
![Captura de pantalla que muestra la actualización in situ completada correctamente.](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a>Paso 6: Reiniciar servicios en todos los servidores actualizados

> [!NOTE]
> Antes de reiniciar los servicios, asegúrese de que%ProgramData%\WindowsFabric no existe en todos los servidores front-end. Si existe, elimínelo antes de iniciar los servicios. 
  
- Después de actualizar todos los servidores en el grupo de servidores front-end, reinicie los servicios con el siguiente comando de PowerShell: 
    
  ```powershell
  Start-CsPool
  ```

    > [!NOTE]
    > Si aún se encuentra pendiente un reinicio del sistema antes de empezar la ejecución de la actualización local, esta no le solicitará el reinicio al final de la instalación. De esta manera, se provocarán excepciones de ensamblado en el primer servidor front-end cuando intente iniciar los servicios con el cmdlet Start-CSPool. Para resolver estos errores, reinicie todos los servidores del grupo y ejecute nuevamente el cmdlet. 
  
- En los servidores de los demás grupos, reinicie los servicios con el siguiente comando:
    
  ```powershell
  Start-CsWindowsService
  ```

Cuando haga clic en **Aceptar** en la página de actualización local, verá el siguiente recordatorio para que complete este paso.
  
![Captura de pantalla que muestra los siguientes pasos una vez finalizada correctamente la actualización in situ.](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a>Paso 7: comprobar la funcionalidad de Skype empresarial

Para asegurarse de que la actualización se realizó correctamente, para el grupo que se actualizó, pruebe Skype empresarial para asegurarse de que la funcionalidad funciona según lo esperado. 
  
### <a name="step-8-upgrade-secondary-pools"></a>Paso 8: Actualizar grupos secundarios

Repita los pasos de este tema para actualizar cualquier grupo adicional que tenga en su entorno.
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a>Solución de problemas con la actualización local

Si se produce un error en la actualización local, es posible que vea un mensaje similar al de la siguiente imagen. 
  
![Captura de pantalla que muestra el fallo de una actualización in situ porque no se ha instalado una actualización acumulada requerida.](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
Revise el mensaje completo que aparece en la parte inferior de la pantalla para solucionar el problema. Haga clic en **Ver registros** para obtener más información.
  
Si se produce un error en la actualización local al **comprobar la preparación** de la actualización o la instalación de los **requisitos previos que faltan**, asegúrese de que el servidor tiene todas las actualizaciones más recientes de Windows Server, Lync Server y SQL Server aplicadas y de que está instalado el software y los roles necesarios. Para obtener una lista de lo que se requiere, consulte [requisitos del servidor para Skype empresarial server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) e [Instale los requisitos previos para skype empresarial Server 2015](install/install-prerequisites.md).
  
## <a name="see-also"></a>Vea también

[Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md)
  
[Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Instalar requisitos previos para Skype Empresarial Server 2015](install/install-prerequisites.md)
  
[Instalar Skype Empresarial Server 2015](install/install.md)
