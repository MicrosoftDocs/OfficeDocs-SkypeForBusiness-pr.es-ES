---
title: Actualizar a Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: 'Resumen: Conozca cómo actualizar desde Lync Server 2013 a Skype para Business Server 2015. Descargue una prueba gratuita de Skype para Business Server 2015 desde el centro de Evaluation de Microsoft en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: f3c451e0c1590daab2c6576964c1e1ce5ec3c4ec
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="upgrade-to-skype-for-business-server-2015"></a>Actualizar a Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo actualizar Lync Server 2013 a Skype para Business Server 2015. Descargue una prueba gratuita de Skype para Business Server 2015 desde el [Centro de evaluación de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Utilice los procedimientos de este documento para actualizar de Lync Server 2013 a Skype para Business Server 2015 utilizando el Skype para el generador de topología de servidor empresarial y la nueva característica de actualización In-situ. Si desea actualizar de Lync Server 2010 o Office Communications Server 2007 R2, vea [previsto actualizar a Skype para Business Server 2015](../plan-your-deployment/upgrade.md).
  
## <a name="upgrade-from-lync-server-2013"></a>Actualización de Lync Server 2013

Actualización de Lync Server 2013 a Skype para Business Server 2015 implica la instalación del software necesario, utilizando el Skype para el generador de topología de servidor de negocios para actualizar las bases de datos en el grupo y utilizando el Skype para actualización In-situ de Business Server en cada uno de los servidores asociados al grupo. Para completar la actualización, siga los ocho pasos descritos en este tema.
  
### <a name="before-you-begin"></a>Antes de comenzar

- Revisar [previsto actualizar a Skype para Business Server 2015](../plan-your-deployment/upgrade.md).
    
- Revise los [requisitos del servidor para Skype para Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- [Instalar los requisitos previos para Skype para Business Server 2015](install/install-prerequisites.md) .
    
- [Instalar Skype para Business Server 2015](install/install.md) .
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a>Paso 1: Instalar las herramientas de administrador y descargar la topología

1. Conectarse al equipo en la topología que carece de Lync OCSCore u otros componentes de Lync instalados.
    
2. De Skype para los medios de instalación de Business Server 2015, ejecute **Setup.exe** desde **OCS_Volume\Setup\AMD64**. 
    
3. Haga clic en **Instalar**. 
    
4. Acepte el acuerdo de licencia.
    
5. En el asistente de implementación, haga clic en **Instalar herramientas de administrador** y siga todos los pasos indicados.
    
     ![Captura de pantalla del Asistente para la implementación con enlace a Instalar herramientas de administrador activado.](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. Desde la pantalla de inicio de Windows, abra Skype para el generador de topología de servidor empresarial.
    
7. Haga clic en **Descargar topología desde implementación existente** y haga clic en **Siguiente**.
    
8. Introduzca un nombre para la topología y haga clic en **Guardar**.
    
9. Vaya a la ubicación donde ha guardado la topología y cree una copia de la misma.
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a>Paso 2: Actualizar y publicar la topología con el Generador de topologías

Antes de iniciar el proceso de actualización, deben ejecutar todos los servicios para los grupos que desea actualizar. El objetivo es que los cambios en la topología se repliquen en las bases de datos locales de los servidores del grupo.
  
> [!IMPORTANT]
>  Guarde una copia del archivo con la topología antes de actualizar. Después de la actualización, no podrá degradar la topología. > Si los servicios están en los mismos servidores que las bases de datos, al igual que el servicio está en el mismo servidor que la base de datos persistente Chat persistente Chat omitir este paso y vaya al paso 4. Después de detener los servicios, ejecute la instalación de la actualización local en cada uno de los servidores para actualizar las bases de datos locales.
  
> [!NOTE]
> Si la topología tiene una base de datos back-end que se refleja, verá tanto la base de datos principal como la reflejada al **publicar la topología** con el Generador de topologías. Asegúrese de que todas las bases de datos se estén ejecutando en la principal y seleccione solo la principal, no el reflejo, cuando publique la topología, de lo contrario verá una advertencia después de publicarla.
  
Elija una de las opciones siguientes para actualizar y publicar una nueva topología mediante el Skype para el generador de topología de Business Server 2015. Cuando complete los pasos y haya publicado la topología actualizada, vaya al paso 3 de este tema.
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a>Opción 1: Actualizar un grupo front-end aislado y los almacenes de archivado y supervisión asociados

Si el grupo que está actualizando tiene una dependencia respecto a un almacén de archivado y supervisión, dicho almacén también se actualizará al realizar los pasos siguientes.
  
1. Generador de topología, haga clic en un grupo de Lync Server 2013, seleccione **actualizar a Skype para Business Server 2015**y siga los pasos. 
    
     ![Captura de pantalla del menú contextual con opción de actualización de Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. Generador de topología, haga clic en la **acción** > **topología de publicar** o **acción** > **topología** > **Publicar**. 
    
     ![Captura de pantalla del menú Acción con la opción Publicar topología en Topology Builder.](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. Durante la publicación, elija instalar una base de datos en el almacén de archivado y supervisión.
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a>Opción 2: Grupo actualización de Front-End sin actualizar Archiving y supervisión de almacenes

Si sigue los siguientes pasos, el archivado y la supervisión del grupo seleccionado quedarán deshabilitados. Tras la actualización, el grupo no tendrá almacén de archivado y supervisión.
  
1. Generador de topología, seleccione el grupo de 2013 de Lync Server que desea actualizar.
    
2. Quitar la dependencia a las tiendas de Lync Server 2013 Archiving y supervisión. 
    
   - Ir a la **acción** > **Editar propiedades**.
    
   - Desmarque la casilla **Archivado**.
    
     ![Captura de pantalla de la casilla de verificación Archivado del cuadro de diálogo Editar propiedades.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - Desmarque la casilla **Supervisión**.
    
     ![Captura de pantalla del cuadro de diálogo Editar propiedades que en la que aparece la casilla de verificación Supervisión.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Haga clic derecho en el grupo de Lync Server 2013, seleccione **actualizar a Skype para Business Server 2015**y siga los pasos. 
    
     ![Captura de pantalla del menú contextual con opción de actualización de Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. Generador de topología, haga clic en la **acción** > **topología de publicar** o **acción** > **topología** > **Publicar**. 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a>Opción 3: Grupo actualización de Front-End y la asocia a Skype nuevos almacenes Business Server 2015 Archiving y supervisión

Si sigue los pasos siguientes, se interrumpirá el archivado y supervisión en el almacén anterior y se iniciará en un nuevo almacén que haya creado. 
  
1. Generador de topología, seleccione el grupo de 2013 de Lync Server que desea actualizar. 
    
2. Quitar la dependencia a las tiendas de Lync Server 2013 Archiving y supervisión. 
    
   - Ir a la **acción** > **Editar propiedades**.
    
   - Desmarque la casilla **Archivado**.
    
     ![Captura de pantalla de la casilla de verificación Archivado del cuadro de diálogo Editar propiedades.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - Desmarque la casilla **Supervisión**.
    
     ![Captura de pantalla del cuadro de diálogo Editar propiedades que en la que aparece la casilla de verificación Supervisión.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Haga clic derecho en el grupo de Lync Server 2013, seleccione **actualizar a Skype para Business Server 2015**y siga los pasos. 
    
     ![Captura de pantalla del menú contextual con opción de actualización de Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. Cree un nuevo almacén SQL para archivado. 
    
   - Seleccione el grupo y la **acción** > **Editar propiedades**. 
    
   -  Marque la casilla **Archivado**.
    
   - Haga clic en **Nuevo**.
    
     ![Captura de pantalla del cuadro de diálogo Editar propiedades en la que aparece el botón Nuevo bajo la sección de archivado.](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. Cree un nuevo almacén SQL para supervisión. 
    
   - Seleccione el grupo y la **acción** > **Editar propiedades**. 
    
   -  Marque la casilla **Supervisión**.
    
   - Haga clic en **Nuevo**.
    
     ![Captura de pantalla del cuadro de diálogo Editar propiedades en la que aparece el botón Nuevo bajo la sección de supervisión.](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. Generador de topología, haga clic en la **acción** > **topología de publicar** o **acción** > **topología** > **Publicar**. 
    
7. Durante la publicación, elija instalar la base de datos en el nuevo almacén de archivado y supervisión.
    
### <a name="step-3-wait-for-replication"></a>Paso 3: Esperar la replicación

Espere un tiempo para que la topología actualizada se publique en todos los servidores del entorno.
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a>Paso 4: Detener todos los servicios en el grupo a actualizar

En cada servidor que atiende el grupo que va a actualizar, ejecute el siguiente cmdlet de PowerShell:
  
```
Disable-CsComputer -Scorch
```

Se recomienda utilizar deshabilitar CsComputer porque puede que necesite reiniciar el servidor durante el proceso de actualización en contexto. Si utiliza Stop-CsWindowsService, algunos servicios se reinician automáticamente después de reiniciar el equipo. Esto puede provocar la actualización In situ a fallar.
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a>Paso 5: Actualizar grupos front-end y servidores de grupos que no son front-end

> [!NOTE]
>  Antes de actualizar instale todos los nuevos requisitos previos requeridos por Skype para Business Server 2015 que incluyen: > al menos 32GB de espacio libre antes de intentar una actualización. Además, asegúrese de que la unidad es una unidad local fija, no está conectada mediante USB o Firewire, está formateada con el sistema de archivos NTFS, no se comprime y no contiene un archivo de página. > PowerShell versión 6.2.9200.0 o posterior. > la más reciente de Lync Server 2013 Actualización acumulativa instalada. > instalado el SP1 de SQL Server 2012. > los siguiente KB instalado (instala automáticamente si usa Microsoft Update): > Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)> Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)> Windows 2012 Server R2 -[KB2982006](https://support.microsoft.com/kb/2982006)
  
Utilice la actualización en contexto en cada servidor para actualizar el grupo de servidores Front-End, piscina de borde, servidor de mediación y el grupo de Chat persistentes.
  
1. En cada servidor, ejecute **Setup.exe** desde **OCS_Volume\Setup\amd64** en el Skype para los medios de instalación de Business Server 2015.
    
2. Acepte el contrato de licencia y siga las instrucciones para la actualización en contexto.
    
3. Repita estos pasos para cada servidor en el grupo de servidores Front-End y en cada servidor del grupo no Front-End.
    
> [!NOTE]
> Es posible que se le solicite que reinicie el servidor durante la actualización local. Es normal. Después de reiniciar, la actualización en contexto continuará desde donde se quedó. 
  
Cuando la actualización local se complete correctamente, verá el siguiente mensaje.
  
![Captura de pantalla que muestra la actualización in situ completada correctamente.](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a>Paso 6: Reiniciar servicios en todos los servidores actualizados

> [!NOTE]
> Antes de reiniciar los servicios, asegúrese de que %ProgramData%\WindowsFabric no existe en todos los servidores frontales. Si existe, elimínelo antes de iniciar los servicios. 
  
- Después de haber actualizado todos los servidores del grupo de Front-End, reinicie los servicios utilizando el siguiente comando de PowerShell: 
    
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
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a>Paso 7: Comprobar Skype para obras de funcionalidad de negocios

Skype para empresas para asegurarse de que la funcionalidad de prueba para asegurarse de que la actualización tuvo éxito, para el grupo que se haya actualizado, funciona como está previsto. 
  
### <a name="step-8-upgrade-secondary-pools"></a>Paso 8: Actualizar grupos secundarios

Repita los pasos de este tema para actualizar cualquier grupo adicional que tenga en su entorno.
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a>Solución de problemas con la actualización local

Si se produce un error en la actualización local, es posible que vea un mensaje similar al de la siguiente imagen. 
  
![Captura de pantalla que muestra el fallo de una actualización in situ porque no se ha instalado una actualización acumulada requerida.](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
Revise el mensaje completo que aparece en la parte inferior de la pantalla para solucionar el problema. Haga clic en **Ver registros** para obtener más información.
  
Si la actualización In situ se produce un error en la **comprobación de preparación de actualización** o ** instalar los requisitos previos que faltan **, asegúrese de que el servidor tiene todas las más recientes de Windows Server, Lync Server y actualizaciones de SQL Server y el software necesario y los roles son instalado. Para obtener una lista de lo que se requiere, consulte [requisitos del servidor para Skype para Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) e [Instalar requisitos previos de Skype para Business Server 2015](install/install-prerequisites.md).
  
## <a name="see-also"></a>Vea también

#### 

[Plan de actualización a Skype para Business Server 2015](../plan-your-deployment/upgrade.md)
  
[Requisitos del servidor para Skype para Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Instalar los requisitos previos para Skype para Business Server 2015](install/install-prerequisites.md)
  
[Instalar Skype para Business Server 2015](install/install.md)

