---
title: Planear la actualización a Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c62b5f6a-bdbe-4ac1-aabf-89e560e64a26
description: 'Resumen: Obtenga información sobre lo que debe tener en cuenta al planear una actualización a Skype empresarial Server 2015. Descargue una prueba gratuita de Skype empresarial Server 2015 en el centro de evaluación de Microsoft en https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server:.'
ms.openlocfilehash: 0f7473bac98ede76763a3f5bda8aee3484c3c03f
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2019
ms.locfileid: "35222134"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>Planear la actualización a Skype Empresarial Server 2015
 
Resumen: Obtenga información sobre lo que debe tener en cuenta al planear una actualización a Skype empresarial Server 2015. Descargue una prueba gratuita de Skype empresarial Server 2015 en el centro de evaluación de Microsoft en [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server):.
  
Como parte de su plan para actualizar a Skype empresarial Server 2015, use este tema para conocer las rutas de actualización recomendadas para Skype empresarial Server 2015, cómo funciona la actualización local, cuáles son los escenarios de coexistencia admitidos y qué es el proceso de actualización. tiene el siguiente aspecto.

> [!NOTE]
> Las actualizaciones locales estaban disponibles en Skype empresarial Server 2015, pero ya no son compatibles con Skype empresarial Server 2019. Se admite la coexistencia en paralelo, consulte [migración a Skype empresarial Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) para obtener más información.
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>Rutas de actualización recomendadas para Skype empresarial Server 2015

 Para actualizar Lync Server 2013, Lync Server 2010 u Office Communications Server 2007 R2 a Skype empresarial Server 2015, use las siguientes rutas de actualización:
  
> [!CAUTION]
> La actualización local mueve de forma automática los directorios de conferencias de Lync Server 2013 a Skype Empresarial Server 2015. Pero, si tiene pensado mover los directorios de conferencias de forma manual, es sumamente importante que use el Shell de administración de Skype Empresarial Server 2015. Si trata de usar el Shell de administración de Lync Server 2013 para mover los directorios de conferencias de Lync Server 2013 a Skype Empresarial Server 2015 se puede producir una pérdida de datos. Normalmente, siempre que trabaje con Skype Empresarial Server 2015 en cualquier capacidad es preciso usar el conjunto de herramientas de Skype Empresarial Server 2015.  
  
|**Versión**|**Recomendaciones**|
|:-----|:-----|
|Lync Server 2013  <br/> | Para actualizar, use el generador de topologías de Skype empresarial Server y la nueva característica de actualización local en cada uno de los servidores asociados con el grupo. vea [planear la actualización de Lync Server 2013 a Skype empresarial server 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013) y [actualizar a skype empresarial Server 2015](../deploy/upgrade-to-skype-for-business-server.md) para conocer los pasos detallados. <br/> |
|Lync Server 2010 + Lync Server 2013 (modo dual)  <br/> |En primer lugar, actualice a Lync Server 2013 y, a continuación, actualice a Skype empresarial Server 2015 con la nueva característica de actualización local. Pero, si la topología es Lync Server 2010 principal, también puede revertir los componentes de Lync Server 2013 a Lync Server 2010 y, después, actualizar directamente a Skype Empresarial Server 2015. En este caso, no podría usar la actualización local, sino que tendría que usar la coexistencia directa entre Lync Server 2010 y Skype Empresarial Server 2015. La existencia triple no es compatible, pero la coexistencia sí que se admite.  <br/> |
|Lync Server 2010  <br/> |Abrir un nuevo grupo de Skype Empresarial Server 2015 y migrar usuarios a este nuevo grupo de servidores. A continuación, puede retirar el antiguo grupo de servidores Lync Server 2010. La actualización de Lync Server 2010 a Skype Empresarial Server 2015 es similar a la actualización de Lync Server 2010 a Lync Server 2013. Vea [migración de Lync server 2010 a Lync server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).  <br/> |
|Office Communications Server 2007 R2  <br/> | Elija una de estas dos opciones: <br/>  Configurar un nuevo entorno de Skype empresarial Server 2015. <br/>  O bien, si su hardware y software cumplen con los requisitos para Skype empresarial Server 2015, actualice a Lync Server 2013 y, después, actualice a Skype empresarial Server 2015 con la nueva característica de actualización local. Para obtener más información, consulte [requisitos del servidor para Skype empresarial server 2015](requirements-for-your-environment/server-requirements.md) y [migración de Office Communications Server 2007 R2 a Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526616).  <br/> |
   
> [!NOTE]
> SQL Server 2014 es compatible con Skype empresarial Server 2015, pero no es compatible con Lync Server 2013. Si desea actualizar de SQL Server 2012 a SQL Server 2014, el grupo debe actualizarse primero a Skype empresarial Server 2015 con el método de actualización local que se describe en este documento. Después, puede actualizar de SQL Server 2012 a SQL Server 2014, vea [actualizar a SQL server 2014](https://msdn.microsoft.com/en-us/library/bb677622%28v=sql.120%29.aspx). Para obtener más información sobre los requisitos de base de datos, consulte [requisitos del servidor para Skype empresarial Server 2015](requirements-for-your-environment/server-requirements.md). 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>Plan de actualización de Lync Server 2013 a Skype Empresarial Server 2015
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Puede actualizar los sistemas de Lync Server 2013 a Skype empresarial Server 2015 con la nueva característica de actualización local. La actualización en contexto proporciona una solución con un solo clic que realiza copias de seguridad de los certificados, desinstala los componentes del servidor, actualiza las bases de datos locales e instala las funciones de Skype empresarial Server 2015. La actualización local pretende preservar las inversiones existentes en el hardware y el servidor, lo que reduce el costo total de la implementación de Skype empresarial Server 2015.
  
> [!NOTE]
> La actualización local le permite usar el mismo hardware al actualizar a Skype empresarial Server. Sin embargo, volver a usar el mismo hardware no se traduce en la misma capacidad de rendimiento. No debería esperar que las cargas de rendimiento para Lync Server 2013 y Skype empresarial Server 2015 sean idénticas. 
  
> [!NOTE]
> La actualización local no es compatible con la alta disponibilidad ni la recuperación ante desastres de Skype empresarial Server. 
  
La actualización local implica desconectar el grupo de servidores de Lync Server 2013 y actualizarlo a un grupo de servidores de Skype empresarial 2015. 
  
### <a name="create-an-in-place-upgrade-plan"></a>Crear un plan de actualización local

Cree un plan que incluya lo siguiente:
  
1. Comprensión de su topología actual.
    
    > [!NOTE]
    > Asegúrese de desinstalar la herramienta de administración de LRS para Lync Server 2013 antes de ejecutar la actualización local. La herramienta de administración LRS para Lync Server 2013 no puede coexistir con Skype empresarial Server 2015. Después de ejecutar la actualización en contexto, instale la nueva herramienta de administración de LRS. Para obtener más información, consulte [portal web administrativo del sistema de Microsoft Lync Room para Skype empresarial Server 2015](https://go.microsoft.com/fwlink/?LinkID=544807) .
  
2. El grupo primario para la actualización.
    
3. Decidir si se actualizan las bases de datos de archivado y supervisión o se crean unas nuevas.
    
4. El método de actualización local que usará: Mover usuarios o Sin conexión. Como parte de Mover usuarios, tendrá que también migrar los directorios de conferencia globales asociados con el grupo principal. 
    
5. Un plan de comunicación con los usuarios afectados.
    
6. Un plan de emergencia en caso de que la actualización falle.
    
Los usuarios en el grupo principal no podrán utilizar los servicios hasta que la actualización se complete. Si dispone de un grupo secundario en funcionamiento, puede evitar que los usuarios se vean afectados trasladándolos a dicho grupo antes de comenzar la actualización. Después de la actualización, vuelva a colocar los usuarios en el repositorio principal.
  
### <a name="in-place-upgrade-methods"></a>Métodos de actualización local

Existen dos escenarios para la actualización local: 
  
- El método Mover usuarios, en el que no hay tiempo de inactividad. 
    
- El método Sin conexión, en el que sí hay tiempo de inactividad.
    
Recomendamos que el método Sin conexión se realice en horario de mantenimiento y que se informe a los usuarios del tiempo de inactividad.
  
> [!NOTE]
> Si actualiza un grupo emparejado en Lync Server 2013 y desea actualizar ambos grupos de Skype Empresarial Server 2015, asegúrese de actualizar el segundo grupo inmediatamente después de actualizar el primero. Cuando un grupo está ejecutando Lync Server 2013 y el segundo grupo se está ejecutando Skype Empresarial Server 2015, las opciones de recuperación ante desastres se minimizan. Por ejemplo, si un grupo de servidores ejecuta 2013 y el segundo es 2015, si se produce un desastre, podrían perderse datos porque el grupo conmutación por error no se admite en modo de desastre cuando los grupos emparejados no son de la misma versión. 
  
#### <a name="in-place-upgrade-offline-method"></a>Método Sin conexión de actualización local

Use este método si no quiere mover a los usuarios de un grupo a otro. Durante la actualización, los usuarios no podrán usar los servicios de Lync o Skype empresarial. 
  
El siguiente diagrama muestra información general sobre este proceso.
  
![Lync 2013 a Skype: usuarios sin conexión](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> Si tiene grupos emparejados, no los desempareje antes de la actualización. 
  
Cuando inicie la actualización de un grupo de servidores, debe completar la actualización para todo el grupo. Skype empresarial Server no es compatible con la actualización de una parte del grupo. 
  
#### <a name="move-users-method-no-user-downtime"></a>Método Mover usuarios (sin tiempo de inactividad)
<a name="bkmk_MoveUsersMethod"> </a>

Este método consiste en mover a los usuarios a otro grupo antes de comenzar la actualización. Durante la actualización, los usuarios pueden usar los servicios de Lync. Una vez que se hayan movido al grupo actualizado, pueden usar Skype empresarial. El siguiente diagrama resume el proceso.
  
> [!IMPORTANT]
> Como parte de Mover usuarios, también tendrá que migrar los directorios de conferencia globales asociados con el grupo principal. Las conferencias de acceso telefónico local RTC aún se resolverán en el id. de conferencia del grupo que se está actualizando, en lugar de en el grupo emparejado. Por lo tanto, necesita mover los directorios de conferencia, en caso de que aún desee proporcionar acceso a las conferencias de RTC programadas en el grupo durante la actualización. 
  
![Diagrama de carriles de natación que muestra a los usuarios que se transfieren a otro grupo antes de la actualización del primer grupo y se devuelven a esta tras dicha actualización.](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>Mover a los usuarios para actualizar el hardware
<a name="bkmk_MoveUsersMethod"> </a>

 Si su hardware no cumple los [requisitos de servidor de Skype empresarial server 2015](requirements-for-your-environment/server-requirements.md), configure un nuevo entorno de Skype empresarial Server 2015 y mueva los usuarios allí. El siguiente diagrama muestra información general sobre este proceso para la actualización desde Lync Server 2010. 
  
![Diagrama de carriles de natación en el que aparecen los usuarios del grupo de servidores front-end principal de Lync Server durante su traslado a Skype Empresarial Server 2015 y el grupo de Lync Server que se está retirando.](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>Proceso de actualización local

 Actualice de Lync Server 2013 a Skype empresarial Server 2015 siguiendo estos pasos:
  
1. Antes de la actualización, realice una copia de seguridad de todas las bases de datos.
    
2. Asegúrese de que todos los servicios que va a actualizar se estén ejecutando.
    
3. Actualice y publique el archivo de topología usando el Generador de topología.
    
4. Detenga todos los servicios en los servidores front-end.
    
5. Instale los nuevos requisitos previos necesarios para Skype empresarial Server.
    
6. Inicie la actualización local en cada uno de los servidores front-end.
    
7. Cuando se complete la actualización, reinicie todos los servicios.
    
   - En el caso del grupo front-end, reinicie los servicios con el comando Start-CsPool.
    
   - Para los servidores de los demás grupos, use Start-CSWindowsService.
    
> [!NOTE]
>  Si no quiere actualizar las bases de datos existentes de archivado y supervisión, elimine esta dependencia antes de actualizar la topología. Si quiere crear nuevas bases de datos de archivado y supervisión, durante la actualización puede crear un nuevo almacén SQL y asociarlo al grupo. Puede encontrar los pasos que se describen en este artículo en el tema[actualización a Skype empresarial Server 2015](../deploy/upgrade-to-skype-for-business-server.md). > actualización local no es compatible con la alta disponibilidad ni la recuperación ante desastres de Skype empresarial Server. Para evitar interrumpir los servicios de los usuarios, use el [método para mover usuarios (sin tiempo de inactividad del usuario)](upgrade.md#bkmk_MoveUsersMethod) para actualizar. > durante el proceso de actualización: XDS-Replica se coloca en la carpeta compartida local de la unidad de disco con más espacio libre. Si el disco se desconecta posteriormente, pueden producirse problemas (por ejemplo, servicios que no se inicien).
  
### <a name="upgrade-order"></a>Orden de actualización

Actualice la topología del interior al exterior. Actualice primero sus grupos, después los servidores perimetrales y, por último, el grupo Almacén de administración central (CMS). 
  
### <a name="kerberos-authentication-considerations"></a>Consideraciones respecto a la autenticación Kerberos

Si usa la autenticación Kerberos en los servicios web, será necesario reasignar las cuentas de Kerberos y restablecer la contraseña después de la actualización local. Para obtener información sobre cómo hacerlo, consulte [configurar la autenticación Kerberos](https://go.microsoft.com/fwlink/p/?LinkId=530342).
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>Compatibilidad con la coexistencia con Lync Server 2013 y Lync Server 2010
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Puede ejecutar Skype Empresarial Server 2015 en la misma topología que Lync Server 2013 o Lync Server 2010, pero no puede tener los tres en la misma topología.
  
Si Lync Server 2010 y Lync Server 2013 coexisten en la misma topología, se recomienda actualizarla por completo a Lync Server 2013, y después actualizar a Skype Empresarial Server 2015 con la actualización local. Para obtener más información, consulte [migración de Lync server 2010 a Lync server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).
  
Si la topología está principalmente en Lync Server 2010, revierta los componentes de Lync Server 2013 a Lync Server 2010 antes de actualizarla a Skype Empresarial Server 2015. En este caso, pierde el beneficio de la actualización local y tiene una topología de coexistencia entre Lync Server 2010 y Skype Empresarial Server 2015.
  
El siguiente diagrama muestra la compatibilidad de coexistencia de Skype empresarial Server 2015 con Lync Server 2013 y Lync Server 2010.
  
![Un diagrama que muestra que se admite la coexistencia de Skype Empresarial Server 2015 con Lync Server 2013 o Lync Server 2010.](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>Proceso de actualización con un servidor y una aplicación de sucursal con funciones de supervivencia
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Skype empresarial Server 2015 no es compatible con la actualización en contexto de un dispositivo de sucursal con supervivencia (SBA) o un servidor de sucursal (SBS) que sea reviviente.
  
No obstante, no admitimos la coexistencia de los centros de datos de Skype Empresarial Server con una SBA o un SBS de Lync Server 2010 o Lync Server 2013. 
  
Al planificar una actualización local de un grupo de Lync Server 2013 Front End (FE) con una sucursal asociada, puede dejar los usuarios existentes en la SBA o el SBS de Lync Server 2013 SBA/SBS. Durante la actualización, los usuarios de la SBA o el SBS entrarán en el modo de resistencia y volverán al funcionamiento normal después de completada la actualización. Para obtener más información sobre la experiencia de los usuarios durante el modo de resistencia, consulte [características de resistencia de sitio de sucursal en Lync Server 2013](https://technet.microsoft.com/library/gg398715.aspx).
  
Al migrar una topología de Lync Server 2010 a Skype Empresarial Server 2015, deben volver a agregarse a la topología la SBA o el SBS, de forma similar a la migración a Lync Server 2013. Para conocer los pasos necesarios, lea la sección sobre la conexión de una [aplicación de rama supervivientes a Lync Server 2013](https://technet.microsoft.com/library/jj688026.aspx).
  
Para las topologías de coexistencia de Lync Server 2010 y Lync Server 2013, primero debe alinear las recomendaciones hechas en la sección ' compatibilidad para la coexistencia con Lync Server 2013 y Lync Server 2010 '.
  
## <a name="see-also"></a>Vea también
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

[Actualizar a Skype Empresarial Server 2015](../deploy/upgrade-to-skype-for-business-server.md)
  
[Environmental requirements for Skype for Business Server 2015](requirements-for-your-environment/environmental-requirements.md)
  
[Server requirements for Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md)
