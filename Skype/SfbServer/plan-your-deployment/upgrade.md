---
title: Planear la actualización a Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: c62b5f6a-bdbe-4ac1-aabf-89e560e64a26
description: 'Resumen: Conozca las cosas que debe tener en cuenta cuando se planea una actualización a Skype para Business Server 2015. Descargue una prueba gratuita de Skype para Business Server 2015 desde el centro de Evaluation de Microsoft en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 81ab68c2fc128016d83962894074c0771e2977d9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>Planear la actualización a Skype Empresarial Server 2015
 
Resumen: Conozca las cosas que debe tener en cuenta cuando se planea una actualización a Skype para Business Server 2015. Descargue una prueba gratuita de Skype para Business Server 2015 desde el centro de Evaluation de Microsoft en: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Como parte de su plan de actualización a Skype para Business Server 2015, utilice este tema para comprender cómo las rutas de actualización recomendadas para Skype para Business Server 2015, los trabajos de actualización en contexto, ¿cuáles son los escenarios de coexistencia compatibles y qué el proceso de actualización aspecto.
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>Rutas de actualización recomendados para Skype para Business Server 2015

 Para actualizar desde Office Communications Server 2007 R2, Lync Server 2010 o Lync Server 2013 a Skype para Business Server 2015, utilice las rutas de actualización siguientes:
  
> [!CAUTION]
> La actualización local mueve de forma automática los directorios de conferencias de Lync Server 2013 a Skype Empresarial Server 2015. Pero, si tiene pensado mover los directorios de conferencias de forma manual, es sumamente importante que use el Shell de administración de Skype Empresarial Server 2015. Si trata de usar el Shell de administración de Lync Server 2013 para mover los directorios de conferencias de Lync Server 2013 a Skype Empresarial Server 2015 se puede producir una pérdida de datos. Normalmente, siempre que trabaje con Skype Empresarial Server 2015 en cualquier capacidad es preciso usar el conjunto de herramientas de Skype Empresarial Server 2015. 
  
|**Versión**|**Recomendaciones**|
|:-----|:-----|
|Lync Server 2013  <br/> | Para actualizar, utilice el Skype para el generador de topología de servidor empresarial y la nueva característica Actualizar In situ en cada uno de los servidores asociados con el grupo. Para ver pasos detallados, consulte [pensado actualizar desde Lync Server 2013 a Skype para Business Server 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013) y [actualizar a Skype para Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md) . <br/> |
|Lync Server 2010 + Lync Server 2013 (modo dual)  <br/> |En primer lugar, actualizar a Lync Server 2013 y, a continuación, actualizar a Skype Business Server 2015 mediante la nueva característica de actualización In-situ. Pero, si la topología es Lync Server 2010 principal, también puede revertir los componentes de Lync Server 2013 a Lync Server 2010 y, después, actualizar directamente a Skype Empresarial Server 2015. En este caso, no podría usar la actualización local, sino que tendría que usar la coexistencia directa entre Lync Server 2010 y Skype Empresarial Server 2015. La existencia triple no es compatible, pero la coexistencia sí que se admite.  <br/> |
|Lync Server 2010  <br/> |Abrir un nuevo grupo de Skype Empresarial Server 2015 y migrar usuarios a este nuevo grupo de servidores. A continuación, puede retirar el antiguo grupo de servidores Lync Server 2010. La actualización de Lync Server 2010 a Skype Empresarial Server 2015 es similar a la actualización de Lync Server 2010 a Lync Server 2013. Vea [migración de Lync Server 2010 para Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).  <br/> |
|Office Communications Server 2007 R2  <br/> | Elija una de dos opciones: <br/>  Configurar un nuevo Skype para entorno Business Server 2015. <br/>  O bien, si el hardware y el software cumplen los requisitos de Skype para Business Server 2015, actualizar a Lync Server 2013 y, a continuación, actualizar a Skype Business Server 2015 mediante la nueva característica de actualización In-situ. Para obtener más información, consulte [requisitos del servidor para Skype para Business Server 2015](requirements-for-your-environment/server-requirements.md) y la [migración de Office Communications Server 2007 R2 a Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526616).  <br/> |
   
> [!NOTE]
> 2014 de SQL Server es compatible con Skype para Business Server 2015 pero no se admite en Lync Server 2013. Si desea actualizar desde SQL Server 2012 a 2014 de SQL Server, a continuación, el grupo debe primero actualizarse a Skype para Business Server 2015 utilizando el método de actualización In situ, tal como se describe en este documento. A continuación, puede actualizar de SQL Server 2012 a 2014 de SQL Server, vea [actualizar a SQL Server 2014](https://msdn.microsoft.com/en-us/library/bb677622%28v=sql.120%29.aspx). Para obtener más información sobre los requisitos de base de datos, consulte [requisitos del servidor para Skype para Business Server 2015](requirements-for-your-environment/server-requirements.md). 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>Plan de actualización de Lync Server 2013 a Skype Empresarial Server 2015
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Puede actualizar los sistemas de Lync Server 2013 a Skype para Business Server 2015 mediante la nueva característica de actualización In-situ. Actualización in situ ofrece una solución de un solo clic que realiza una copia de los certificados, desinstala los componentes del servidor, actualiza las bases de datos locales e instala el Skype para funciones de servidor de negocios 2015. Actualización in situ intenta conservar el hardware existente y las inversiones en servidores, reduce los costos generales para implementar Skype para Business Server 2015.
  
> [!NOTE]
> Actualización in-situ permite utilizar el mismo hardware al actualizar a Skype para Business Server. Sin embargo, volver a usar el mismo hardware no se traduce en la misma capacidad de rendimiento. Usted no debe esperar las cargas de rendimiento para Lync Server 2013 y Skype para Business Server 2015 para que sean idénticos. 
  
> [!NOTE]
> Actualización en contexto no soporta alta disponibilidad ni recuperación ante desastres para Skype para Business Server. 
  
Actualización in situ implica poner fuera de conexión el grupo de Lync Server 2013 y actualizarlo a un Skype para grupo Business Server 2015. 
  
### <a name="create-an-in-place-upgrade-plan"></a>Crear un plan de actualización local

Crear un plan que incluya:
  
1. Comprensión de la topología actual.
    
    > [!NOTE]
    > Asegúrese de desinstalar la herramienta de administración de LRS para Lync Server 2013 antes de ejecutar la actualización en contexto. La herramienta de administración de LRS para Lync Server 2013 no puede coexistir con Skype para Business Server 2015. Después de ejecutar la actualización In-situ, instalar la nueva herramienta de administración de LRS, consulte [Microsoft Lync sala sistema administrativo Portal Web de Skype para Business Server 2015](https://go.microsoft.com/fwlink/?LinkID=544807)
  
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
    
Se recomienda que se programe una actualización del método sin conexión durante el mantenimiento y el tiempo de inactividad notificar a los usuarios.
  
> [!NOTE]
> Si actualiza un grupo emparejado en Lync Server 2013 y desea actualizar ambos grupos de Skype Empresarial Server 2015, asegúrese de actualizar el segundo grupo inmediatamente después de actualizar el primero. Cuando un grupo está ejecutando Lync Server 2013 y el segundo grupo se está ejecutando Skype Empresarial Server 2015, las opciones de recuperación ante desastres se minimizan. Por ejemplo, si un grupo de servidores ejecuta 2013 y el segundo es 2015, si se produce un desastre, podrían perderse datos porque el grupo conmutación por error no se admite en modo de desastre cuando los grupos emparejados no son de la misma versión. 
  
#### <a name="in-place-upgrade-offline-method"></a>Método Sin conexión de actualización local

Use este método si no quiere mover a los usuarios de un grupo a otro. Durante la actualización, los usuarios no podrán utilizar Lync o Skype para servicios empresariales. 
  
El siguiente diagrama muestra información general sobre este proceso.
  
![Lync 2013 a Skype: usuarios sin conexión](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> Si tiene grupos emparejados, no los desempareje antes de la actualización. 
  
Cuando inicie la actualización de un grupo de servidores, debe completar la actualización para todo el grupo. Skype para Business Server no es compatible con tener sólo una parte de la agrupación actualizada. 
  
#### <a name="move-users-method-no-user-downtime"></a>Método Mover usuarios (sin tiempo de inactividad)
<a name="bkmk_MoveUsersMethod"> </a>

Este método consiste en mover a los usuarios a otro grupo antes de comenzar la actualización. Durante la actualización, los usuarios pueden utilizar servicios de Lync. Después de que se mueven a la piscina actualizada, pueden utilizar Skype para empresas. El siguiente diagrama resume el proceso.
  
> [!IMPORTANT]
> Como parte de Mover usuarios, también tendrá que migrar los directorios de conferencia globales asociados con el grupo principal. Las conferencias de acceso telefónico local RTC aún se resolverán en el id. de conferencia del grupo que se está actualizando, en lugar de en el grupo emparejado. Por lo tanto, necesita mover los directorios de conferencia, en caso de que aún desee proporcionar acceso a las conferencias de RTC programadas en el grupo durante la actualización. 
  
![Diagrama de carriles de natación que muestra a los usuarios que se transfieren a otro grupo antes de la actualización del primer grupo y se devuelven a esta tras dicha actualización.](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>Mover a los usuarios para actualizar el hardware
<a name="bkmk_MoveUsersMethod"> </a>

 Si su hardware no cumple los [requisitos del servidor para Skype para Business Server 2015](requirements-for-your-environment/server-requirements.md), configurar un nuevo Skype para entorno Business Server 2015 y mover usuarios. El siguiente diagrama muestra información general sobre este proceso para la actualización desde Lync Server 2010. 
  
![Diagrama de carriles de natación en el que aparecen los usuarios del grupo de servidores front-end principal de Lync Server durante su traslado a Skype Empresarial Server 2015 y el grupo de Lync Server que se está retirando.](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>Proceso de actualización local

 Actualizar desde Lync Server 2013 a Skype para Business Server 2015 siguiendo estos pasos:
  
1. Antes de la actualización, realice una copia de seguridad de todas las bases de datos.
    
2. Asegúrese de que todos los servicios que va a actualizar se estén ejecutando.
    
3. Actualice y publique el archivo de topología usando el Generador de topología.
    
4. Detenga todos los servicios en los servidores front-end.
    
5. Instalar nuevos requisitos previos requeridos por Skype para Business Server.
    
6.  Inicie la actualización local en cada uno de los servidores front-end.
    
7. Cuando se complete la actualización, reinicie todos los servicios.
    
  - En el caso del grupo front-end, reinicie los servicios con el comando Start-CsPool.
    
  - Para los servidores de los demás grupos, use Start-CSWindowsService.
    
> [!NOTE]
>  Si no quiere actualizar las bases de datos existentes de archivado y supervisión, elimine esta dependencia antes de actualizar la topología. Si quiere crear nuevas bases de datos de archivado y supervisión, durante la actualización puede crear un nuevo almacén SQL y asociarlo al grupo. Puede encontrar los pasos sobre cómo hacer esto en el tema,[actualizar a Skype para Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md). > Actualización en contexto no admite alta disponibilidad, o recuperación ante desastres para Skype para Business Server. Para evitar la interrupción de los servicios de los usuarios, utilice el [método de mover usuarios (sin tiempo de inactividad de usuario)](upgrade.md#bkmk_MoveUsersMethod) para actualización. > durante el proceso de actualización de la réplica de xds se coloca en la carpeta compartida local en la unidad de disco con más espacio libre. Si el disco se desconecta posteriormente, pueden producirse problemas (por ejemplo, servicios que no se inicien).
  
### <a name="upgrade-order"></a>Orden de actualización

Actualizar la topología desde el interior hacia el exterior. Actualice primero sus grupos, después los servidores perimetrales y, por último, el grupo Almacén de administración central (CMS). 
  
### <a name="kerberos-authentication-considerations"></a>Consideraciones respecto a la autenticación Kerberos

Si usa la autenticación Kerberos en los servicios web, será necesario reasignar las cuentas de Kerberos y restablecer la contraseña después de la actualización local. Para saber cómo hacerlo, consulte [configuración de la autenticación Kerberos](https://go.microsoft.com/fwlink/p/?LinkId=530342).
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>Soporte para la coexistencia con Lync Server 2013 y Lync Server 2010
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Puede ejecutar Skype Empresarial Server 2015 en la misma topología que Lync Server 2013 o Lync Server 2010, pero no puede tener los tres en la misma topología.
  
Si Lync Server 2010 y Lync Server 2013 coexisten en la misma topología, se recomienda actualizarla por completo a Lync Server 2013, y después actualizar a Skype Empresarial Server 2015 con la actualización local. Para obtener más información, consulte [migración de Lync Server 2010 para Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).
  
Si la topología está principalmente en Lync Server 2010, revierta los componentes de Lync Server 2013 a Lync Server 2010 antes de actualizarla a Skype Empresarial Server 2015. En este caso, pierde el beneficio de la actualización local y tiene una topología de coexistencia entre Lync Server 2010 y Skype Empresarial Server 2015.
  
El diagrama siguiente muestra la compatibilidad de coexistencia de Skype para Business Server 2015 con Lync Server 2013 y Lync Server 2010.
  
![Un diagrama que muestra que se admite la coexistencia de Skype Empresarial Server 2015 con Lync Server 2013 o Lync Server 2010.](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>Proceso de actualización con un servidor y una aplicación de sucursal con funciones de supervivencia
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Skype para Business Server 2015 no admite una actualización In situ de un servidor de sucursal que puede perdurar (SBS) o de un dispositivo de sucursal funciones de supervivencia (SBA).
  
No obstante, no admitimos la coexistencia de los centros de datos de Skype Empresarial Server con una SBA o un SBS de Lync Server 2010 o Lync Server 2013. 
  
Al planificar una actualización local de un grupo de Lync Server 2013 Front End (FE) con una sucursal asociada, puede dejar los usuarios existentes en la SBA o el SBS de Lync Server 2013 SBA/SBS. Durante la actualización, los usuarios de la SBA o el SBS entrarán en el modo de resistencia y volverán al funcionamiento normal después de completada la actualización. Para obtener más información acerca de la experiencia de los usuarios durante el modo de resistencia, consulte [características de resistencia del sitio de la sucursal en Lync Server 2013](https://technet.microsoft.com/library/gg398715.aspx).
  
Al migrar una topología de Lync Server 2010 a Skype Empresarial Server 2015, deben volver a agregarse a la topología la SBA o el SBS, de forma similar a la migración a Lync Server 2013. Para los pasos necesarios, lea [Conectar dispositivo de sucursal que sobreviven al grupo 2013 Front End de Lync Server](https://technet.microsoft.com/library/jj688026.aspx).
  
Para topologías de coexistencia de Lync Server 2010 y Lync Server 2013, alinear primero las recomendaciones realizadas en la sección 'Soporte para la coexistencia con Lync Server 2013 y Lync Server 2010'.
  
## <a name="see-also"></a>Vea también
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

#### 

[Actualización de Skype para Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md)
  
[Requisitos ambientales para Skype para Business Server 2015](requirements-for-your-environment/environmental-requirements.md)
  
[Requisitos del servidor para Skype para Business Server 2015](requirements-for-your-environment/server-requirements.md)

