---
title: Actualizar a Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: 'Resumen: Obtenga información sobre cómo realizar una actualización de Lync Server 2013 Skype para Business Server 2015. Descargue una versión de prueba gratuita de Skype para Business Server 2015 desde el Evaluation de Microsoft center en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 36d692788e84c0e7f136d947d7c3b2709b490b9f
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19501080"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a>Actualizar a Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo actualizar de Lync Server 2013 a Skype para Business Server 2015. Descargue una versión de prueba gratuita de Skype para Business Server 2015 desde el [Centro de evaluación de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Use los procedimientos descritos en este documento para actualizar desde Lync Server 2013 a Skype para Business Server 2015 con el Skype para Business Server Topology Builder y la nueva característica de actualización en contexto. Si desea actualizar desde Office Communications Server 2007 R2 o de Lync Server 2010, vea [Planear la actualización a Skype para Business Server 2015](../plan-your-deployment/upgrade.md).
  
## <a name="upgrade-from-lync-server-2013"></a>Actualización de Lync Server 2013

Actualización de Lync Server 2013 a Skype para Business Server 2015 implica instalar el software necesario como requisito previo, usa el Skype para Business Server Topology Builder para actualizar las bases de datos en el grupo de servidores y usa el Skype para actualización en contexto de servidor de Business en cada uno de los servidores asociados con el grupo de servidores. Para completar la actualización, siga los ocho pasos descritos en este tema.
  
### <a name="before-you-begin"></a>Antes de comenzar

- Revisar el [Plan para actualizar a Skype para Business Server 2015](../plan-your-deployment/upgrade.md).
    
- Revise [los requisitos de servidor de Skype para Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- [Instalar los requisitos previos de Skype para Business Server 2015](install/install-prerequisites.md) .
    
- [Instalar Skype para Business Server 2015](install/install.md) .
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a>Paso 1: Instalar las herramientas de administrador y descargar la topología

1. Conectar al equipo en la topología que no tiene Lync OCSCore o todos los componentes de Lync instalados.
    
2. De Skype para los medios de instalación de Business Server 2015, ejecute **Setup.exe** desde **OCS_Volume\Setup\AMD64**. 
    
3. Haga clic en **Instalar**. 
    
4. Acepte el acuerdo de licencia.
    
5. En el asistente de implementación, haga clic en **Instalar herramientas de administrador** y siga todos los pasos indicados.
    
     ![Captura de pantalla del Asistente para la implementación con enlace a Instalar herramientas de administrador activado.](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. En la pantalla de inicio de Windows, abra Skype para Business Server Topology Builder.
    
7. Haga clic en **Descargar topología desde implementación existente** y haga clic en **Siguiente**.
    
8. Introduzca un nombre para la topología y haga clic en **Guardar**.
    
9. Vaya a la ubicación donde ha guardado la topología y cree una copia de la misma.
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a>Paso 2: Actualizar y publicar la topología con el Generador de topologías

Antes de comenzar el proceso de actualización, deben ejecutar todos los servicios para los grupos de que planear la actualización. El objetivo es que los cambios en la topología se repliquen en las bases de datos locales de los servidores del grupo.
  
> [!IMPORTANT]
>  Guarde una copia del archivo con la topología antes de actualizar. Después de la actualización, no podrá degradar la topología. > Si los servicios se encuentran en los mismos servidores según las bases de datos, como los de Chat persistente servicio está en el mismo servidor que la base de datos de Chat persistente, omita este paso y vaya al paso 4. Después de detener los servicios, ejecute la instalación de la actualización local en cada uno de los servidores para actualizar las bases de datos locales.
  
> [!NOTE]
> Si la topología tiene una base de datos back-end que se refleja, verá tanto la base de datos principal como la reflejada al **publicar la topología** con el Generador de topologías. Asegúrese de que todas las bases de datos se estén ejecutando en la principal y seleccione solo la principal, no el reflejo, cuando publique la topología, de lo contrario verá una advertencia después de publicarla.
  
Elija una de las opciones siguientes para actualizar y publicar una topología nueva mediante el uso de la Skype para Business Server 2015 Topology Builder. Cuando complete los pasos y haya publicado la topología actualizada, vaya al paso 3 de este tema.
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a>Opción 1: Actualizar un grupo front-end aislado y los almacenes de archivado y supervisión asociados

Si el grupo que está actualizando tiene una dependencia respecto a un almacén de archivado y supervisión, dicho almacén también se actualizará al realizar los pasos siguientes.
  
1. En el generador, haga clic en un grupo de servidores de Lync Server 2013, seleccione **actualizar a Skype para Business Server 2015**y siga los pasos. 
    
     ![Captura de pantalla del menú contextual con opción de actualización de Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. En el generador, haga clic en **acción** > **Publicar topología** o **acción** > **topología** > **Publicar**. 
    
     ![Captura de pantalla del menú Acción con la opción Publicar topología en Topology Builder.](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. Durante la publicación, elija instalar una base de datos en el almacén de archivado y supervisión.
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a>La opción 2: Grupo de servidores actualización de Front-End sin actualizar almacenes de supervisión y archivado

Si sigue los siguientes pasos, el archivado y la supervisión del grupo seleccionado quedarán deshabilitados. Tras la actualización, el grupo no tendrá almacén de archivado y supervisión.
  
1. En el generador, seleccione el grupo de Lync Server 2013 que desea actualizar.
    
2. Quitar la dependencia para los almacenes de Lync Server 2013 archivado y supervisión. 
    
   - Vaya a la **acción** > **Editar propiedades**.
    
   - Desmarque la casilla **Archivado**.
    
     ![Captura de pantalla de la casilla de verificación Archivado del cuadro de diálogo Editar propiedades.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - Desmarque la casilla **Supervisión**.
    
     ![Captura de pantalla del cuadro de diálogo Editar propiedades que en la que aparece la casilla de verificación Supervisión.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Haga clic en el grupo de servidores de Lync Server 2013, seleccione **actualizar a Skype para Business Server 2015**y siga los pasos. 
    
     ![Captura de pantalla del menú contextual con opción de actualización de Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. En el generador, haga clic en **acción** > **Publicar topología** o **acción** > **topología** > **Publicar**. 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a>La opción 3: Grupo de servidores actualización de Front-End y la asocia a nuevo Skype para almacenes Business Server 2015 archivado y supervisión

Si sigue los pasos siguientes, se interrumpirá el archivado y supervisión en el almacén anterior y se iniciará en un nuevo almacén que haya creado. 
  
1. En el generador, seleccione el grupo de Lync Server 2013 que desea actualizar. 
    
2. Quitar la dependencia para los almacenes de Lync Server 2013 archivado y supervisión. 
    
   - Vaya a la **acción** > **Editar propiedades**.
    
   - Desmarque la casilla **Archivado**.
    
     ![Captura de pantalla de la casilla de verificación Archivado del cuadro de diálogo Editar propiedades.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - Desmarque la casilla **Supervisión**.
    
     ![Captura de pantalla del cuadro de diálogo Editar propiedades que en la que aparece la casilla de verificación Supervisión.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Haga clic en el grupo de servidores de Lync Server 2013, seleccione **actualizar a Skype para Business Server 2015**y siga los pasos. 
    
     ![Captura de pantalla del menú contextual con opción de actualización de Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. Cree un nuevo almacén SQL para archivado. 
    
   - Seleccione el grupo de servidores y la **acción** > **Editar propiedades**. 
    
   -  Marque la casilla **Archivado**.
    
   - Haga clic en **Nuevo**.
    
     ![Captura de pantalla del cuadro de diálogo Editar propiedades en la que aparece el botón Nuevo bajo la sección de archivado.](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. Cree un nuevo almacén SQL para supervisión. 
    
   - Seleccione el grupo de servidores y la **acción** > **Editar propiedades**. 
    
   -  Marque la casilla **Supervisión**.
    
   - Haga clic en **Nuevo**.
    
     ![Captura de pantalla del cuadro de diálogo Editar propiedades en la que aparece el botón Nuevo bajo la sección de supervisión.](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. En el generador, haga clic en **acción** > **Publicar topología** o **acción** > **topología** > **Publicar**. 
    
7. Durante la publicación, elija instalar la base de datos en el nuevo almacén de archivado y supervisión.
    
### <a name="step-3-wait-for-replication"></a>Paso 3: Esperar la replicación

Espere un tiempo para que la topología actualizada se publique en todos los servidores del entorno.
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a>Paso 4: Detener todos los servicios en el grupo a actualizar

En cada servidor que realiza el grupo de servidores que va a actualizar, ejecute el siguiente cmdlet de PowerShell:
  
```
Disable-CsComputer -Scorch
```

Se recomienda usar Disable-CsComputer porque es posible que necesite reiniciar el servidor durante el proceso de actualización en contexto. Si utiliza Stop-CsWindowsService, algunos servicios se reinician automáticamente después de un reinicio. Esto puede provocar la actualización en contexto se lleve a cabo.
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a>Paso 5: Actualizar grupos front-end y servidores de grupos que no son front-end

> [!NOTE]
>  Antes de actualizar instale todos los nuevos requisitos previos necesarios para Skype para 2015 de servidor empresarial que incluyen: > al menos 32GB de espacio libre antes de intentar una actualización. Además, asegúrese de que la unidad es una unidad local fija, no está conectada mediante USB o Firewire, tiene el formato con el sistema de archivos NTFS, no se comprime y no contiene un archivo de página. > PowerShell versión 6.2.9200.0 o posterior. > la versión más reciente de Lync Server 2013 Actualización acumulativa instalada. > SQL Server 2012 SP1 instalado. > los siguiente KB instalado (se instala automáticamente si se usa Microsoft Update): > Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)> Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)> Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)
  
Use la actualización en contexto en cada servidor para actualizar el grupo de servidores Front-End, grupo de servidores perimetrales, el servidor de mediación y el grupo de Chat persistente.
  
1. En cada servidor, ejecute **Setup.exe** desde **OCS_Volume\Setup\amd64** en el Skype para los medios de instalación de Business Server 2015.
    
2. Acepte el contrato de licencia y siga las instrucciones para la actualización en contexto.
    
3. Repita estos pasos para cada servidor en el grupo de servidores Front-End y en cada servidor del grupo de servidores que no sean Front-End.
    
> [!NOTE]
> Es posible que se le solicite que reinicie el servidor durante la actualización local. Es normal. Después de reiniciar, la actualización en contexto continuará desde donde se quedó. 
  
Cuando la actualización local se complete correctamente, verá el siguiente mensaje.
  
![Captura de pantalla que muestra la actualización in situ completada correctamente.](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a>Paso 6: Reiniciar servicios en todos los servidores actualizados

> [!NOTE]
> Antes de reiniciar los servicios, asegúrese de que %ProgramData%\WindowsFabric no existe en todos los servidores Front-End. Si existe, elimínelo antes de iniciar los servicios. 
  
- Después de haber actualizado todos los servidores del grupo de servidores Front-End, reinicie los servicios mediante el siguiente comando de PowerShell: 
    
  ```
  Start-CsPool
  ```

    > [!NOTE]
    > Si aún se encuentra pendiente un reinicio del sistema antes de empezar la ejecución de la actualización local, esta no le solicitará el reinicio al final de la instalación. De esta manera, se provocarán excepciones de ensamblado en el primer servidor front-end cuando intente iniciar los servicios con el cmdlet Start-CSPool. Para resolver estos errores, reinicie todos los servidores del grupo y ejecute nuevamente el cmdlet. 
  
- En los servidores de los demás grupos, reinicie los servicios con el siguiente comando:
    
  ```
  Start-CsWindowsService
  ```

Cuando haga clic en **Aceptar** en la página de actualización local, verá el siguiente recordatorio para que complete este paso.
  
![Captura de pantalla que muestra los siguientes pasos una vez finalizada correctamente la actualización in situ.](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a>Paso 7: Comprobar Skype para el funcionamiento de la funcionalidad empresarial

Para asegurarse de que la actualización fue correcta, para el grupo que se ha actualizado, Skype para la empresa para asegurarse de que la funcionalidad de prueba funciona como se esperaba. 
  
### <a name="step-8-upgrade-secondary-pools"></a>Paso 8: Actualizar grupos secundarios

Repita los pasos de este tema para actualizar cualquier grupo adicional que tenga en su entorno.
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a>Solución de problemas con la actualización local

Si se produce un error en la actualización local, es posible que vea un mensaje similar al de la siguiente imagen. 
  
![Captura de pantalla que muestra el fallo de una actualización in situ porque no se ha instalado una actualización acumulada requerida.](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
Revise el mensaje completo que aparece en la parte inferior de la pantalla para solucionar el problema. Haga clic en **Ver registros** para obtener más información.
  
Si la actualización en contexto se produce un error en la **comprobación de preparación de actualización** o ** instalar los requisitos previos que faltan **, asegúrese de que el servidor tiene todos los más recientes de Windows Server, Lync Server y las actualizaciones de SQL Server que se aplican, y todos los roles son la software requerido instalado. Para obtener una lista de lo que se requiere, vea [requisitos de servidor para Skype para Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) e [instalar los requisitos previos para Skype para Business Server 2015](install/install-prerequisites.md).
  
## <a name="see-also"></a>Vea también

[Plan para actualizar a Skype para Business Server 2015](../plan-your-deployment/upgrade.md)
  
[Requisitos de servidor de Skype para Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Instalar los requisitos previos de Skype para Business Server 2015](install/install-prerequisites.md)
  
[Instalar Skype para Business Server 2015](install/install.md)