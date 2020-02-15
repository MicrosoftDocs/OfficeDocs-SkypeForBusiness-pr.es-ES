---
title: Planeación de la actualización a Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c62b5f6a-bdbe-4ac1-aabf-89e560e64a26
description: 'Resumen: Obtenga información sobre los aspectos que debe tener en cuenta al planear una actualización a Skype empresarial Server 2015. Descargue una versión de prueba gratuita de Skype empresarial Server 2015 desde el centro de evaluación de https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverMicrosoft en:.'
ms.openlocfilehash: 91cc78f22c03bf7ec59c9ac0c936f194ece71a35
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030644"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>Planeación de la actualización a Skype empresarial Server 2015
 
Resumen: Obtenga información sobre los aspectos que debe tener en cuenta al planear una actualización a Skype empresarial Server 2015. Descargue una versión de prueba gratuita de Skype empresarial Server 2015 desde el centro de evaluación de [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)Microsoft en:.
  
Como parte del plan para actualizar a Skype empresarial Server 2015, use este tema para comprender las rutas de actualización recomendadas a Skype empresarial Server 2015, cómo funciona la actualización en el mismo, qué son los escenarios de coexistencia admitidos y qué proceso de actualización es similar a.

> [!NOTE]
> Las actualizaciones locales estaban disponibles en Skype empresarial Server 2015, pero ya no se admiten en Skype empresarial Server 2019. Se admite la coexistencia en paralelo, consulte [migración a Skype empresarial Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) para obtener más información.
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>Rutas de actualización recomendadas para Skype empresarial Server 2015

 Para actualizar desde Lync Server 2013, Lync Server 2010 o Office Communications Server 2007 R2 a Skype empresarial Server 2015, use las siguientes rutas de actualización:
  
> [!CAUTION]
> La actualización inmediata mueve automáticamente los directorios de conferencia de Lync Server 2013 a Skype empresarial Server 2015. Sin embargo, si tiene previsto mover manualmente los directorios de conferencia, es muy importante usar el shell de administración de Skype empresarial Server 2015. Si intenta usar el shell de administración de Lync Server 2013 para mover los directorios de conferencia de Lync Server 2013 a Skype empresarial Server 2015, puede producirse la pérdida de datos. En general, cada vez que trabaje con Skype empresarial Server 2015 en cualquier capacidad debe usar el conjunto de herramientas de Skype empresarial Server 2015.  
  
|**Version**|**Recomendaciones**|
|:-----|:-----|
|Lync Server 2013  <br/> | Para actualizar, use el generador de topologías de Skype empresarial Server y la nueva característica de actualización local en cada uno de los servidores asociados con el grupo. consulte [plan to upgrade from Lync server 2013 to Skype for Business server 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013) y [Upgrade to Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md) para conocer los pasos detallados. <br/> |
|Lync Server 2010 + Lync Server 2013 (modo dual)  <br/> |En primer lugar, actualice a Lync Server 2013 y, a continuación, actualice a Skype empresarial Server 2015 mediante la nueva característica de actualización local. Sin embargo, si la topología es principal Lync Server 2010, también puede revertir los componentes de Lync Server 2013 a Lync Server 2010 y, a continuación, actualizar directamente a Skype empresarial Server 2015. En este caso, no podría aprovechar la actualización local y se usaría la coexistencia directa entre Lync Server 2010 y Skype empresarial Server 2015. No se admite Tri-existencia, pero se admite la coexistencia.  <br/> |
|Lync Server 2010  <br/> |Abra un nuevo grupo de servidores de Skype empresarial Server 2015 y, a continuación, migre los usuarios a este nuevo grupo. A continuación, puede retirar el grupo de servidores de Lync Server 2010 antiguo. La actualización de Lync Server 2010 a Skype empresarial Server 2015 es similar a la actualización de Lync Server 2010 a Lync Server 2013. Consulte [migración de Lync server 2010 a Lync server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).  <br/> |
|Office Communications Server 2007 R2  <br/> | Seleccione una de las dos opciones: <br/>  Configure un nuevo entorno de Skype empresarial Server 2015. <br/>  O bien, si el hardware y el software cumplen con los requisitos de Skype empresarial Server 2015, actualice a Lync Server 2013 y, a continuación, actualice a Skype empresarial Server 2015 mediante la nueva característica de actualización local. Para obtener más información, consulte [requisitos del servidor para Skype empresarial Server 2015](requirements-for-your-environment/server-requirements.md) y [migración de Office Communications Server 2007 R2 a Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526616).  <br/> |
   
> [!NOTE]
> SQL Server 2014 se admite en Skype empresarial Server 2015 pero no es compatible con Lync Server 2013. Si desea actualizar de SQL Server 2012 a SQL Server 2014, el grupo debe actualizarse primero a Skype empresarial Server 2015 mediante el método de actualización local tal y como se describe en este documento. A continuación, puede actualizar desde SQL Server 2012 a SQL Server 2014, vea [actualizar a SQL server 2014](https://msdn.microsoft.com/library/bb677622%28v=sql.120%29.aspx). Para obtener más información acerca de los requisitos de bases de datos, consulte [Server Requirements for Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md). 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>Planeación de la actualización de Lync Server 2013 a Skype empresarial Server 2015
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Puede actualizar los sistemas Lync Server 2013 a Skype empresarial Server 2015 mediante la nueva característica de actualización local. La actualización inmediata proporciona una solución de un solo clic que realiza una copia de seguridad de los certificados, desinstala los componentes del servidor, actualiza las bases de datos locales e instala los roles de Skype empresarial Server 2015. La actualización local pretende preservar las inversiones existentes en el hardware y el servidor, lo que reduce el costo general de la implementación de Skype empresarial Server 2015.
  
> [!NOTE]
> La actualización local le permite usar el mismo hardware al actualizar a Skype empresarial Server. Sin embargo, la reutilización del mismo hardware no se traduce en la misma capacidad de rendimiento. No es necesario esperar que las cargas de rendimiento para Lync Server 2013 y Skype empresarial Server 2015 sean idénticas. 
  
> [!NOTE]
> La actualización local no es compatible con la alta disponibilidad ni la recuperación ante desastres de Skype empresarial Server. 
  
La actualización local implica poner el grupo de servidores de Lync Server 2013 en modo sin conexión y actualizarlo a un grupo de servidores de Skype empresarial 2015. 
  
### <a name="create-an-in-place-upgrade-plan"></a>Crear un plan de actualización local

Cree un plan que incluya lo siguiente:
  
1. Conocimientos de la topología actual.
    
    > [!NOTE]
    > Asegúrese de desinstalar la herramienta de administración de LRS para Lync Server 2013 antes de ejecutar la actualización local. La herramienta de administración de LRS para Lync Server 2013 no puede coexistir con Skype empresarial Server 2015. Después de ejecutar la actualización local, instale la nueva herramienta de administración de LRS. Consulte el [portal web administrativo del sistema Microsoft Lync Room para Skype empresarial Server 2015](https://go.microsoft.com/fwlink/?LinkID=544807) para obtener más información.
  
2. El grupo de servidores principal para la actualización.
    
3. Si va a actualizar las bases de datos de archivado y supervisión, o si va a crear otras nuevas.
    
4. El método de actualización local que va a usar: sin conexión o mover usuarios. Como parte de mover usuarios, también tendrá que migrar los directorios de conferencia global asociados con el grupo principal. 
    
5. Un plan de comunicación para los usuarios afectados.
    
6. Un plan de copia de seguridad en caso de que se produzca un error en las actualizaciones.
    
Los usuarios que se encuentren en el grupo de servidores principal mientras se actualizan no podrán usar los servicios hasta que se complete la actualización. Si tiene un grupo secundario en funcionamiento, puede evitar que los usuarios se vean afectados si los mueve al segundo grupo antes de la actualización. Después de la actualización, vuelva a mover a los usuarios al grupo principal.
  
### <a name="in-place-upgrade-methods"></a>Métodos de actualización local

Hay dos escenarios para la actualización local: 
  
- El método de mover usuarios, que no requiere tiempo de inactividad para los usuarios. 
    
- El método sin conexión, que requiere tiempo de inactividad.
    
Recomendamos que se programe una actualización del método sin conexión durante un período de mantenimiento y los usuarios reciban notificaciones del tiempo de inactividad.
  
> [!NOTE]
> Al actualizar un grupo emparejado en Lync Server 2013 y desea actualizar ambos grupos a Skype empresarial Server 2015. Asegúrese de actualizar el segundo grupo de servidores inmediatamente después de actualizar el primer grupo. Cuando un grupo ejecuta Lync Server 2013 y el segundo grupo ejecuta Skype empresarial Server 2015, se minimizan las opciones de recuperación ante desastres. Por ejemplo, si un grupo de servidores ejecuta 2013 y el segundo es 2015 y hay un desastre, puede experimentar la pérdida de datos porque la conmutación por error del grupo no se admite en el modo de desastre cuando los grupos emparejados no tienen la misma versión. 
  
#### <a name="in-place-upgrade-offline-method"></a>Método sin conexión de actualización local

Use este método si no desea mover usuarios entre grupos de usuarios. Durante la actualización, los usuarios no podrán usar los servicios de Lync o Skype empresarial. 
  
En el siguiente diagrama se muestra una descripción general de este proceso.
  
![Lync 2013 a usuarios de Skype sin conexión](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> Si tiene grupos emparejados, no los desempareja antes de la actualización. 
  
Una vez que comience la actualización de un grupo de servidores, debe completar la actualización de todo el grupo. Skype empresarial Server no admite tener solo una parte del grupo de servidores actualizada. 
  
#### <a name="move-users-method-no-user-downtime"></a>Método Move users (sin tiempo de inactividad del usuario)
<a name="bkmk_MoveUsersMethod"> </a>

Para usar este método, mueva usuarios a otro grupo antes de comenzar la actualización. Durante la actualización, los usuarios pueden usar los servicios de Lync. Una vez que se han movido al grupo actualizado, pueden usar Skype empresarial. En el siguiente diagrama se muestra una descripción general de este proceso.
  
> [!IMPORTANT]
> Como parte de mover usuarios, también tendrá que migrar los directorios de conferencia global asociados con el grupo principal. La Conferencia de acceso telefónico local de RTC seguirá resolviendo ConferenceID en el grupo que se está actualizando, en lugar del grupo emparejado. Por lo tanto, tiene que mover los directorios de conferencia, si todavía desea que las conferencias RTC programadas en el grupo sean accesibles durante la actualización. 
  
![Diagrama de nadar que muestra a los usuarios que se mueven a otro grupo antes de que se actualice el grupo y se muevan de vuelta al grupo después de actualizarse.](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>Mover usuarios para la actualización de hardware
<a name="bkmk_MoveUsersMethod"> </a>

 Si el hardware no cumple los [requisitos de servidor de Skype empresarial server 2015](requirements-for-your-environment/server-requirements.md), configure un nuevo entorno de Skype empresarial Server 2015 y mueva los usuarios a él. En el siguiente diagrama se muestra una descripción general de este proceso para actualizar desde Lync Server 2010. 
  
![Diagrama de carril de natación que muestra a los usuarios del grupo de servidores front-end principal de Lync Server que se mueven a Skype empresarial Server 2015 y al grupo de Lync Server que se está retirando.](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>Proceso de actualización local

 Actualice de Lync Server 2013 a Skype empresarial Server 2015 mediante los pasos siguientes:
  
1. Realice una copia de seguridad de todas las bases de datos antes de la actualización.
    
2. Asegúrese de que todos los servicios que se van a actualizar estén en estado de ejecución.
    
3. Actualice y publique el archivo de topología con el generador de topologías.
    
4. Detenga todos los servicios en todos los servidores front-end.
    
5. Instale los nuevos requisitos previos necesarios para Skype empresarial Server.
    
6. En cada servidor front-end, inicie la actualización local.
    
7. Una vez finalizada la actualización, reinicie todos los servicios.
    
   - Para el grupo de servidores front-end, reinicie los servicios con el comando START-CsPool.
    
   - Para los servidores que no sean front-end, use Start-CSWindowsService.
    
> [!NOTE]
>  Si no desea actualizar las bases de datos de archivado y supervisión existentes, quite la dependencia antes de actualizar la topología. Si desea crear nuevas bases de datos de archivado y supervisión, durante la actualización, puede crear un nuevo almacén de SQL y asociarlo con el grupo de servidores. Puede encontrar los pasos que debe seguir en el tema[actualizar a Skype empresarial Server 2015](../deploy/upgrade-to-skype-for-business-server.md). > actualización local no es compatible con la alta disponibilidad ni la recuperación ante desastres de Skype empresarial Server. Para evitar la interrupción de los servicios de los usuarios, use el [Método Move users (sin tiempo de inactividad del usuario)](upgrade.md#bkmk_MoveUsersMethod) para realizar la actualización. > durante el proceso de actualización la réplica XDS se coloca en la carpeta compartida local de la unidad de disco con la mayor cantidad de espacio disponible. Si el disco se quita posteriormente, puede encontrarse con problemas como, por ejemplo, servicios que no se inician.
  
### <a name="upgrade-order"></a>Orden de actualización

Actualice la topología desde el interior al exterior. Actualice primero todos los grupos, a continuación, los servidores perimetrales y, por último, el grupo de almacén de administración central (CMS). 
  
### <a name="kerberos-authentication-considerations"></a>Consideraciones sobre la autenticación Kerberos

Si usa la autenticación Kerberos para los servicios Web, debe reasignar las cuentas de Kerberos y restablecer la contraseña una vez completada la actualización en el sitio. Para obtener información sobre cómo hacerlo, consulte [configuración de la autenticación Kerberos](https://go.microsoft.com/fwlink/p/?LinkId=530342).
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>Compatibilidad para la coexistencia con Lync Server 2013 y Lync Server 2010
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Puede ejecutar Skype empresarial Server 2015 en la misma topología que Lync Server 2013 o Lync Server 2010, pero no puede tener los tres en la misma topología.
  
Si tiene una coexistencia entre Lync Server 2010 y Lync Server 2013, se recomienda actualizar toda la topología a Lync Server 2013 y, a continuación, actualizar a Skype empresarial Server 2015 con la actualización local. Para obtener más información, consulte [migración de Lync server 2010 a Lync server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).
  
Si su topología es principalmente Lync Server 2010, revierta los componentes de Lync Server 2013 a Lync Server 2010 antes de actualizar la topología a Skype empresarial Server 2015. En este caso, se pierde la ventaja de la actualización local y se tiene una topología de coexistencia entre Lync Server 2010 y Skype empresarial Server 2015.
  
El siguiente diagrama muestra la compatibilidad de coexistencia de Skype empresarial Server 2015 con Lync Server 2013 y Lync Server 2010.
  
![Un diagrama que muestra la compatibilidad de coexistencia de Skype empresarial Server 2015 con Lync Server 2013 o Lync Server 2010.](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>Proceso de actualización con un servidor y una aplicación de sucursal con funciones de supervivencia existentes
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Skype empresarial Server 2015 no admite la actualización local de una aplicación de sucursal con funciones de supervivencia (SBA) o un servidor de sucursal con funciones de supervivencia (SBS).
  
Sin embargo, sí admite la coexistencia de centros de recursos de Skype empresarial Server con Lync Server 2010 o Lync Server 2013 SBA/SBS. 
  
Al planear una actualización local de un grupo de servidores front-end (FE) 2013 de Lync Server con una rama asociada, puede dejar a los usuarios existentes en el servidor de Lync Server 2013 SBA/SBS. Durante la actualización, los usuarios de SBA/SBS entrarán en el modo de resistencia y volverán a la funcionalidad normal una vez que se haya completado la actualización. Para obtener más información sobre la experiencia de los usuarios durante el modo de resistencia, consulte [características de resistencia de sitios de sucursal en Lync Server 2013](https://technet.microsoft.com/library/gg398715.aspx).
  
Al migrar una topología de Lync Server 2010 a Skype empresarial Server 2015, SBA/SBS debe volver a agregarse a la topología, de forma similar a la migración a Lync Server 2013. Para conocer los pasos necesarios, consulte [conectar una aplicación de sucursal con funciones de supervivencia a un grupo de servidores front-end de Lync Server 2013](https://technet.microsoft.com/library/jj688026.aspx).
  
Para las topologías de coexistencia de Lync Server 2010 y Lync Server 2013, alinee primero las recomendaciones realizadas en la sección "compatibilidad para la coexistencia con Lync Server 2013 y Lync Server 2010".
  
## <a name="see-also"></a>Consulte también
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

[Actualizar a Skype empresarial Server 2015](../deploy/upgrade-to-skype-for-business-server.md)
  
[Requisitos del entorno para Skype empresarial Server 2015](requirements-for-your-environment/environmental-requirements.md)
  
[Requisitos de servidor para Skype empresarial Server 2015](requirements-for-your-environment/server-requirements.md)
