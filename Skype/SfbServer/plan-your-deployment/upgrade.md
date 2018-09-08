---
title: Planear la actualización a Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c62b5f6a-bdbe-4ac1-aabf-89e560e64a26
description: 'Resumen: Conozca las cosas que debe tener en cuenta al planear una actualización a Skype para Business Server 2015. Descargue una versión de prueba gratuita de Skype para Business Server 2015 desde el Evaluation de Microsoft center en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 437c54513865ceb28f717f50b4619a735720c98b
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882743"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>Planear la actualización a Skype Empresarial Server 2015
 
Resumen: Conozca las cosas que debe tener en cuenta al planear una actualización a Skype para Business Server 2015. Descargue una versión de prueba gratuita de Skype para Business Server 2015 desde el Evaluation de Microsoft center en: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Como parte del plan de actualización a Skype para Business Server 2015, utilice este tema para comprender cómo las rutas de actualización recomendadas para Skype para Business Server 2015, el funcionamiento de la actualización en contexto, ¿cuáles son los escenarios de coexistencia compatibles y qué el proceso de actualización tiene un aspecto.

> [!NOTE]
> Las actualizaciones en contexto estaban disponibles en Skype para Business Server 2015, pero ya no se admiten en Skype para Business Server 2019. En paralelo se admite la coexistencia, consulte [migración de Skype para Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) para obtener más información.
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>Rutas de actualización recomendadas para Skype para Business Server 2015

 Actualización de Lync Server 2013, Lync Server 2010 o Office Communications Server 2007 R2 a Skype para Business Server 2015, use las siguientes rutas de actualización:
  
> [!CAUTION]
> La actualización local mueve de forma automática los directorios de conferencias de Lync Server 2013 a Skype Empresarial Server 2015. Pero, si tiene pensado mover los directorios de conferencias de forma manual, es sumamente importante que use el Shell de administración de Skype Empresarial Server 2015. Si trata de usar el Shell de administración de Lync Server 2013 para mover los directorios de conferencias de Lync Server 2013 a Skype Empresarial Server 2015 se puede producir una pérdida de datos. Normalmente, siempre que trabaje con Skype Empresarial Server 2015 en cualquier capacidad es preciso usar el conjunto de herramientas de Skype Empresarial Server 2015.  
  
|**Versión**|**Recomendaciones**|
|:-----|:-----|
|Lync Server 2013  <br/> | Para actualizar, use la Skype para Business Server Topology Builder y la nueva característica de actualización en contexto en cada uno de los servidores asociados con el grupo de servidores. Para obtener instrucciones detalladas, vea [Planear la actualización de Lync Server 2013 a Skype para Business Server 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013) y [actualizar a Skype para Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md) . <br/> |
|Lync Server 2010 + Lync Server 2013 (modo dual)  <br/> |En primer lugar, actualice a Lync Server 2013 y, a continuación, actualice a Skype para Business Server 2015 mediante el uso de la nueva característica de actualización en contexto. Pero, si la topología es Lync Server 2010 principal, también puede revertir los componentes de Lync Server 2013 a Lync Server 2010 y, después, actualizar directamente a Skype Empresarial Server 2015. En este caso, no podría usar la actualización local, sino que tendría que usar la coexistencia directa entre Lync Server 2010 y Skype Empresarial Server 2015. La existencia triple no es compatible, pero la coexistencia sí que se admite.  <br/> |
|Lync Server 2010  <br/> |Abrir un nuevo grupo de Skype Empresarial Server 2015 y migrar usuarios a este nuevo grupo de servidores. A continuación, puede retirar el antiguo grupo de servidores Lync Server 2010. La actualización de Lync Server 2010 a Skype Empresarial Server 2015 es similar a la actualización de Lync Server 2010 a Lync Server 2013. Vea [migración de Lync Server 2010 a Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).  <br/> |
|Office Communications Server 2007 R2  <br/> | Elija una de estas dos opciones: <br/>  Configurar un nuevo Skype para entorno empresarial Server 2015. <br/>  O bien, si el hardware y el software cumplen los requisitos de Skype para Business Server 2015, actualice a Lync Server 2013 y, a continuación, actualice a Skype para Business Server 2015 mediante el uso de la nueva característica de actualización en contexto. Para obtener más información, vea [requisitos de servidor para Skype para Business Server 2015](requirements-for-your-environment/server-requirements.md) y la [migración de Office Communications Server 2007 R2 a Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526616).  <br/> |
   
> [!NOTE]
> SQL Server 2014 es compatible con en Skype Business Server 2015, pero no se admite en Lync Server 2013. Si desea actualizar desde SQL Server 2012 a SQL Server 2014, a continuación, el grupo de servidores en primer lugar se debe actualizar a Skype para Business Server 2015 mediante el método de actualización en contexto, tal como se describe en este documento. A continuación, puede actualizar desde SQL Server 2012 para SQL Server 2014, vea [actualizar a SQL Server 2014](https://msdn.microsoft.com/en-us/library/bb677622%28v=sql.120%29.aspx). Para obtener más información acerca de los requisitos de la base de datos, vea [requisitos de servidor para Skype para Business Server 2015](requirements-for-your-environment/server-requirements.md). 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>Plan de actualización de Lync Server 2013 a Skype Empresarial Server 2015
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Puede actualizar los sistemas de Lync Server 2013 a Skype para Business Server 2015 mediante la nueva característica de actualización en contexto. Actualización en contexto proporciona una solución de un solo clic que realiza una copia de seguridad de certificados, desinstala los componentes del servidor, actualiza las bases de datos locales e instala el Skype para funciones de Business Server 2015. Actualización en contexto intenta conservar el hardware existente y las inversiones en servidores, reduce los costos generales para implementar Skype para Business Server 2015.
  
> [!NOTE]
> Actualización en contexto permite utilizar el mismo hardware al actualizar a Skype para Business Server. Sin embargo, volver a usar el mismo hardware no se traduce en la misma capacidad de rendimiento. No deben esperar que las cargas de rendimiento para Lync Server 2013 y Skype para Business Server 2015 para que sean idénticos. 
  
> [!NOTE]
> Actualización en contexto no admite alta disponibilidad ni recuperación ante desastres para Skype para Business Server. 
  
Actualización en contexto implica poner sin conexión el grupo de servidores de Lync Server 2013 y actualización a un Skype para el grupo de servidores de Business Server 2015. 
  
### <a name="create-an-in-place-upgrade-plan"></a>Crear un plan de actualización local

Cree un plan que incluya lo siguiente:
  
1. Una descripción de la topología actual.
    
    > [!NOTE]
    > Asegúrese de desinstalar la herramienta de administración de LRS para Lync Server 2013 antes de ejecutar la actualización en contexto. La herramienta de administración de LRS para Lync Server 2013 no puede coexistir con Skype para Business Server 2015. Después de ejecutar la actualización en contexto, instale la nueva herramienta de administración de LRS, consulte [Microsoft Lync salón del sistema administrativo Portal Web para Skype para Business Server 2015](https://go.microsoft.com/fwlink/?LinkID=544807)
  
2. El grupo principal para la actualización.
    
3. Decidir si se actualizan las bases de datos de archivado y supervisión o se crean unas nuevas.
    
4. El método de actualización local que usará: Mover usuarios o Sin conexión. Como parte de Mover usuarios, tendrá que también migrar los directorios de conferencia globales asociados con el grupo principal. 
    
5. Un plan de comunicación con los usuarios afectados.
    
6. Un plan de emergencia en caso de que la actualización falle.
    
Los usuarios en el grupo principal no podrán utilizar los servicios hasta que la actualización se complete. Si dispone de un grupo secundario en funcionamiento, puede evitar que los usuarios se vean afectados trasladándolos a dicho grupo antes de comenzar la actualización. Después de la actualización, mover los usuarios al grupo principal.
  
### <a name="in-place-upgrade-methods"></a>Métodos de actualización local

Existen dos escenarios para la actualización local: 
  
- El método Mover usuarios, en el que no hay tiempo de inactividad. 
    
- El método Sin conexión, en el que sí hay tiempo de inactividad.
    
Recomendamos que el método Sin conexión se realice en horario de mantenimiento y que se informe a los usuarios del tiempo de inactividad.
  
> [!NOTE]
> Si actualiza un grupo emparejado en Lync Server 2013 y desea actualizar ambos grupos de Skype Empresarial Server 2015, asegúrese de actualizar el segundo grupo inmediatamente después de actualizar el primero. Cuando un grupo está ejecutando Lync Server 2013 y el segundo grupo se está ejecutando Skype Empresarial Server 2015, las opciones de recuperación ante desastres se minimizan. Por ejemplo, si un grupo de servidores ejecuta 2013 y el segundo es 2015, si se produce un desastre, podrían perderse datos porque el grupo conmutación por error no se admite en modo de desastre cuando los grupos emparejados no son de la misma versión. 
  
#### <a name="in-place-upgrade-offline-method"></a>Método Sin conexión de actualización local

Use este método si no quiere mover a los usuarios de un grupo a otro. Durante la actualización, los usuarios no podrán usar Lync o Skype para servicios de negocios. 
  
El siguiente diagrama muestra información general sobre este proceso.
  
![Lync 2013 a Skype: usuarios sin conexión](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> Si tiene grupos emparejados, no los desempareje antes de la actualización. 
  
Cuando inicie la actualización de un grupo de servidores, debe completar la actualización para todo el grupo. Skype para Business Server no admite tener sólo una parte del grupo de servidores actualizado. 
  
#### <a name="move-users-method-no-user-downtime"></a>Método Mover usuarios (sin tiempo de inactividad)
<a name="bkmk_MoveUsersMethod"> </a>

Este método consiste en mover a los usuarios a otro grupo antes de comenzar la actualización. Durante la actualización, los usuarios pueden usar servicios de Lync. Después de que se mueven al grupo de servidores actualizado, pueden utilizar Skype para la empresa. El siguiente diagrama resume el proceso.
  
> [!IMPORTANT]
> Como parte de Mover usuarios, también tendrá que migrar los directorios de conferencia globales asociados con el grupo principal. Las conferencias de acceso telefónico local RTC aún se resolverán en el id. de conferencia del grupo que se está actualizando, en lugar de en el grupo emparejado. Por lo tanto, necesita mover los directorios de conferencia, en caso de que aún desee proporcionar acceso a las conferencias de RTC programadas en el grupo durante la actualización. 
  
![Diagrama de carriles de natación que muestra a los usuarios que se transfieren a otro grupo antes de la actualización del primer grupo y se devuelven a esta tras dicha actualización.](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>Mover a los usuarios para actualizar el hardware
<a name="bkmk_MoveUsersMethod"> </a>

 Si su hardware no cumple los [requisitos del servidor para Skype para Business Server 2015](requirements-for-your-environment/server-requirements.md), configurar un nuevo Skype para entorno empresarial Server 2015 y mover los usuarios no existe. El siguiente diagrama muestra información general sobre este proceso para la actualización desde Lync Server 2010. 
  
![Diagrama de carriles de natación en el que aparecen los usuarios del grupo de servidores front-end principal de Lync Server durante su traslado a Skype Empresarial Server 2015 y el grupo de Lync Server que se está retirando.](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>Proceso de actualización local

 Actualizar de Lync Server 2013 a Skype para Business Server 2015 mediante los pasos siguientes:
  
1. Antes de la actualización, realice una copia de seguridad de todas las bases de datos.
    
2. Asegúrese de que todos los servicios que va a actualizar se estén ejecutando.
    
3. Actualice y publique el archivo de topología usando el Generador de topología.
    
4. Detenga todos los servicios en los servidores front-end.
    
5. Instalar nuevos requisitos previos necesarios para Skype para el servidor empresarial.
    
6.  Inicie la actualización local en cada uno de los servidores front-end.
    
7. Cuando se complete la actualización, reinicie todos los servicios.
    
  - En el caso del grupo front-end, reinicie los servicios con el comando Start-CsPool.
    
  - Para los servidores de los demás grupos, use Start-CSWindowsService.
    
> [!NOTE]
>  Si no quiere actualizar las bases de datos existentes de archivado y supervisión, elimine esta dependencia antes de actualizar la topología. Si quiere crear nuevas bases de datos de archivado y supervisión, durante la actualización puede crear un nuevo almacén SQL y asociarlo al grupo. Puede encontrar los pasos sobre cómo hacerlo en el tema,[actualizar a Skype para Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md). > Actualización en contexto no admite alta disponibilidad o recuperación ante desastres para Skype para Business Server. Para evitar la interrupción de los servicios de los usuarios, utilice el [método Move Users (sin tiempo de inactividad de usuario)](upgrade.md#bkmk_MoveUsersMethod) a la actualización. > durante el proceso de actualización de la réplica de xds se coloca en la carpeta compartida local en la unidad de disco con más espacio libre. Si el disco se desconecta posteriormente, pueden producirse problemas (por ejemplo, servicios que no se inicien).
  
### <a name="upgrade-order"></a>Orden de actualización

Actualizar la topología desde el interior al exterior. Actualice primero sus grupos, después los servidores perimetrales y, por último, el grupo Almacén de administración central (CMS). 
  
### <a name="kerberos-authentication-considerations"></a>Consideraciones respecto a la autenticación Kerberos

Si usa la autenticación Kerberos en los servicios web, será necesario reasignar las cuentas de Kerberos y restablecer la contraseña después de la actualización local. Para obtener información sobre cómo hacerlo, consulte [configuración de la autenticación Kerberos](https://go.microsoft.com/fwlink/p/?LinkId=530342).
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>Soporte para la coexistencia con Lync Server 2013 y Lync Server 2010
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Puede ejecutar Skype Empresarial Server 2015 en la misma topología que Lync Server 2013 o Lync Server 2010, pero no puede tener los tres en la misma topología.
  
Si Lync Server 2010 y Lync Server 2013 coexisten en la misma topología, se recomienda actualizarla por completo a Lync Server 2013, y después actualizar a Skype Empresarial Server 2015 con la actualización local. Para obtener más información, vea [migración de Lync Server 2010 a Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).
  
Si la topología está principalmente en Lync Server 2010, revierta los componentes de Lync Server 2013 a Lync Server 2010 antes de actualizarla a Skype Empresarial Server 2015. En este caso, pierde el beneficio de la actualización local y tiene una topología de coexistencia entre Lync Server 2010 y Skype Empresarial Server 2015.
  
En el siguiente diagrama se muestra la compatibilidad de coexistencia de Skype para Business Server 2015 con Lync Server 2013 y Lync Server 2010.
  
![Un diagrama que muestra que se admite la coexistencia de Skype Empresarial Server 2015 con Lync Server 2013 o Lync Server 2010.](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>Proceso de actualización con un servidor y una aplicación de sucursal con funciones de supervivencia
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Skype para Business Server 2015 no admite una actualización en contexto de un dispositivo de sucursal con funciones de supervivencia (SBA) o un servidor de sucursal con funciones de supervivencia (SBS).
  
No obstante, no admitimos la coexistencia de los centros de datos de Skype Empresarial Server con una SBA o un SBS de Lync Server 2010 o Lync Server 2013. 
  
Al planificar una actualización local de un grupo de Lync Server 2013 Front End (FE) con una sucursal asociada, puede dejar los usuarios existentes en la SBA o el SBS de Lync Server 2013 SBA/SBS. Durante la actualización, los usuarios de la SBA o el SBS entrarán en el modo de resistencia y volverán al funcionamiento normal después de completada la actualización. Para obtener más información acerca de la experiencia de los usuarios durante el modo de resistencia, consulte [características de resistencia de sitios de sucursal en Lync Server 2013](https://technet.microsoft.com/library/gg398715.aspx).
  
Al migrar una topología de Lync Server 2010 a Skype Empresarial Server 2015, deben volver a agregarse a la topología la SBA o el SBS, de forma similar a la migración a Lync Server 2013. Para los pasos necesarios, lea la [Conexión de aplicación de sucursal con funciones de supervivencia al grupo de servidores Front-End de Lync Server 2013](https://technet.microsoft.com/library/jj688026.aspx).
  
Para topologías de coexistencia de Lync Server 2010 y Lync Server 2013, alinear primero las recomendaciones realizadas en la sección 'Soporte técnico para la coexistencia con Lync Server 2013 y Lync Server 2010'.
  
## <a name="see-also"></a>Vea también
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

[Actualización de Skype para Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md)
  
[Requisitos del entorno para Skype Empresarial Server 2015](requirements-for-your-environment/environmental-requirements.md)
  
[Requisitos del servidor para Skype Empresarial Server 2015](requirements-for-your-environment/server-requirements.md)