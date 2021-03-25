---
title: Planear la actualización a Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Summary: Learn about the things you should consider when you plan an upgrade to Skype for Business Server 2015. Descargue una versión de prueba gratuita de Skype Empresarial Server 2015 desde el Centro de evaluación de Microsoft en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server .'
ms.openlocfilehash: 742a582c9945e495bf150a174f8bc80101f61f7c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122374"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>Planear la actualización a Skype Empresarial Server 2015
 
Summary: Learn about the things you should consider when you plan an upgrade to Skype for Business Server 2015. Descargue una versión de prueba gratuita de Skype Empresarial Server 2015 desde el Centro de evaluación de Microsoft en: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) .
  
Como parte del plan para actualizar a Skype Empresarial Server 2015, use este tema para comprender las rutas de actualización recomendadas a Skype Empresarial Server 2015, cómo funciona la actualización de In-Place, cuáles son los escenarios de coexistencia admitidos y cómo es el proceso de actualización.

> [!NOTE]
> Las actualizaciones locales estaban disponibles en Skype Empresarial Server 2015, pero ya no se admiten en Skype Empresarial Server 2019. Se admite la coexistencia en paralelo, vea [Migración a Skype Empresarial Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) para obtener más información.
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>Rutas de actualización recomendadas a Skype Empresarial Server 2015

 Para actualizar de Lync Server 2013, Lync Server 2010 u Office Communications Server 2007 R2 a Skype Empresarial Server 2015, use las siguientes rutas de actualización:
  
> [!CAUTION]
> In-Place upgrade mueve automáticamente los directorios de conferencia de Lync Server 2013 a Skype Empresarial Server 2015. Sin embargo, si planea mover manualmente directorios de conferencia, es muy importante usar el Shell de administración de Skype Empresarial Server 2015. Si intenta usar el Shell de administración de Lync Server 2013 para mover directorios de conferencia de Lync Server 2013 a Skype Empresarial Server 2015, puede producirse la pérdida de datos. En general, siempre que trabaje con Skype Empresarial Server 2015 en cualquier capacidad, debe usar el conjunto de herramientas de Skype Empresarial Server 2015.  
  
|**Versión**|**Recomendaciones**|
|:-----|:-----|
|Lync Server 2013  <br/> | Para actualizar, use el Generador de topologías de Skype Empresarial Server y la nueva característica de actualización In-Place en cada uno de los servidores asociados al grupo. vea [Plan to upgrade from Lync Server 2013 to Skype for Business Server 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013) and Upgrade to Skype for Business Server [2015](../deploy/upgrade-to-skype-for-business-server.md) for detailed steps. <br/> |
|Lync Server 2010 + Lync Server 2013 (modo dual)  <br/> |En primer lugar, actualice a Lync Server 2013 y, a continuación, actualice a Skype Empresarial Server 2015 mediante la nueva característica In-Place actualización. Sin embargo, si la topología es la principal de Lync Server 2010, también puede revertir los componentes de Lync Server 2013 a Lync Server 2010 y, a continuación, actualizar directamente a Skype Empresarial Server 2015. En este caso, no podría aprovechar la actualización de In-Place y usaría la coexistencia directa entre Lync Server 2010 y Skype Empresarial Server 2015. No se admite la existencia tri, pero se admite la coexistencia.  <br/> |
|Lync Server 2010  <br/> |Traiga un nuevo grupo de Skype Empresarial Server 2015 y, a continuación, migre usuarios a este nuevo grupo. A continuación, puede retirar el antiguo grupo de servidores de Lync Server 2010. La actualización de Lync Server 2010 a Skype Empresarial Server 2015 es similar a la actualización de Lync Server 2010 a Lync Server 2013. Consulte [Migración de Lync Server 2010 a Lync Server 2013](/previous-versions/office/lync-server-2013/migration-from-lync-server-2010-to-lync-server-2013).  <br/> |
|Office Communications Server 2007 R2  <br/> | Elija una de las dos opciones: <br/>  Configurar un nuevo entorno de Skype Empresarial Server 2015. <br/>  O bien, si el hardware y el software cumplen los requisitos de Skype Empresarial Server 2015, actualice a Lync Server 2013 y, a continuación, actualice a Skype Empresarial Server 2015 mediante la nueva característica de actualización de In-Place. Para obtener más información, vea Requisitos del servidor para [Skype Empresarial Server 2015](requirements-for-your-environment/server-requirements.md) y Migración de [Office Communications Server 2007 R2 a Lync Server 2013](/previous-versions/office/lync-server-2013/migration-from-office-communications-server-2007-r2-to-lync-server-2013).  <br/> |
   
> [!NOTE]
> SQL Server 2014 se admite en Skype Empresarial Server 2015, pero no se admite en Lync Server 2013. Si desea actualizar de SQL Server 2012 a SQL Server 2014, el grupo primero debe actualizarse a Skype Empresarial Server 2015 mediante el método upgrade de In-Place, tal como se describe en este documento. A continuación, puede actualizar de SQL Server 2012 a SQL Server 2014, vea [Upgrade to SQL Server 2014](/sql/database-engine/install-windows/upgrade-sql-server?viewFallbackFrom=sql-server-2014). Para obtener más información sobre los requisitos de la base de datos, vea [Requisitos del servidor para Skype Empresarial Server 2015](requirements-for-your-environment/server-requirements.md). 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>Planear la actualización de Lync Server 2013 a Skype Empresarial Server 2015
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Puede actualizar sistemas de Lync Server 2013 a Skype Empresarial Server 2015 con la nueva característica In-Place actualización. La actualización local proporciona una solución de un solo clic que realiza una copia de seguridad de certificados, desinstala componentes de servidor, actualiza bases de datos locales e instala los roles de Skype Empresarial Server 2015. La actualización local busca conservar las inversiones de hardware y servidor existentes, lo que reduce el costo global para implementar Skype Empresarial Server 2015.
  
> [!NOTE]
> In-Place upgrade le permite usar el mismo hardware al actualizar a Skype Empresarial Server. Sin embargo, la reusación del mismo hardware no se traduce en la misma capacidad de rendimiento. No debe esperar que las cargas de rendimiento de Lync Server 2013 y Skype Empresarial Server 2015 sean idénticas. 
  
> [!NOTE]
> In-Place actualización no admite alta disponibilidad ni recuperación ante desastres para Skype Empresarial Server. 
  
La actualización local implica desconectar el grupo de Lync Server 2013 y actualizarlo a un grupo de Skype Empresarial Server 2015. 
  
### <a name="create-an-in-place-upgrade-plan"></a>Crear un plan In-Place actualización

Haga un plan que incluya:
  
1. Una comprensión de la topología actual.
    
    > [!NOTE]
    > Asegúrese de desinstalar la herramienta de administración de LRS para Lync Server 2013 antes de ejecutar In-Place actualización. La herramienta de administración de LRS para Lync Server 2013 no puede coexistir con Skype Empresarial Server 2015. Después de ejecutar In-Place actualizar instale la nueva herramienta de administración de LRS. Vea [Microsoft Lync Room System Administrative Web Portal for Skype for Business Server 2015](https://go.microsoft.com/fwlink/?LinkID=544807) para obtener más información.
  
2. El grupo de servidores principal para la actualización.
    
3. Tanto si va a actualizar las bases de datos de archivado y supervisión como si va a crear otras nuevas.
    
4. El In-Place upgrade que usará: Sin conexión o Mover usuarios. Como parte de Mover usuarios, también tendrá que migrar los directorios de conferencia global asociados con el grupo de servidores principal. 
    
5. Un plan de comunicación para usuarios afectados.
    
6. Un plan de copia de seguridad en caso de que se produce un error en las actualizaciones.
    
Los usuarios que se encuentran en el grupo de servidores principal mientras se actualiza no podrán usar los servicios hasta que se complete la actualización. Si tiene un grupo secundario de trabajo, puede evitar afectar a los usuarios al moverlos al grupo de servidores secundario antes de la actualización. Después de la actualización, vuelva a mover a los usuarios al grupo de servidores principal.
  
### <a name="in-place-upgrade-methods"></a>Métodos de actualización local

Hay dos escenarios para la actualización In-Place: 
  
- El método Move User, que no requiere tiempo de inactividad para los usuarios. 
    
- El método Offline, que requiere tiempo de inactividad.
    
Se recomienda programar una actualización del método sin conexión durante una ventana de mantenimiento y se notifica a los usuarios del tiempo de inactividad.
  
> [!NOTE]
> Al actualizar un grupo de servidores emparejado en Lync Server 2013 y desea actualizar ambos grupos a Skype Empresarial Server 2015. Asegúrese de actualizar el segundo grupo inmediatamente después de actualizar el primer grupo. Cuando un grupo de servidores ejecuta Lync Server 2013 y el segundo grupo ejecuta Skype Empresarial Server 2015, se minimizan las opciones de recuperación ante desastres. Por ejemplo, si un grupo de servidores ejecuta 2013 y el segundo es 2015 y hay un desastre, podría experimentar pérdida de datos porque la conmutación por error del grupo no se admite en modo desastre cuando los grupos emparejados no son la misma versión. 
  
#### <a name="in-place-upgrade-offline-method"></a>Método sin conexión de actualización local

Use este método si no desea mover usuarios entre grupos de usuarios. Durante la actualización, los usuarios no podrán usar los servicios de Lync o Skype Empresarial. 
  
En el siguiente diagrama se muestra una introducción a este proceso.
  
![Lync 2013 Para usuarios de Skype sin conexión](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> Si ha emparejado grupos de servidores, no los desaparre antes de la actualización. 
  
Una vez que empiece a actualizar un grupo de servidores, debe completar la actualización de todo el grupo. Skype Empresarial Server no admite tener solo una parte del grupo actualizado. 
  
#### <a name="move-users-method-no-user-downtime"></a>Método Move Users (sin tiempo de inactividad del usuario)
<a name="bkmk_MoveUsersMethod"> </a>

Para usar este método, se mueven usuarios a otro grupo antes de iniciar la actualización. Durante la actualización, los usuarios pueden usar los servicios de Lync. Una vez que se han movido al grupo actualizado, pueden usar Skype Empresarial. En el siguiente diagrama se muestra una introducción a este proceso.
  
> [!IMPORTANT]
> Como parte de Mover usuarios, también tendrá que migrar los directorios de conferencia global asociados con el grupo de servidores principal. Las conferencias de acceso telefónico local RTC seguirán resolviendo ConferenceID en el grupo que se va a actualizar, en lugar del grupo emparejado. Por lo tanto, debe mover directorios de conferencia, si todavía desea que las conferencias RTC programadas en el grupo sean accesibles durante la actualización. 
  
![Diagrama de natación que muestra los usuarios que se mueven a otro grupo antes de actualizar el grupo y de volver al grupo después de actualizarlo.](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>Mover usuarios para la actualización de hardware
<a name="bkmk_MoveUsersMethod"> </a>

 Si el hardware no cumple los requisitos de servidor para [Skype Empresarial Server 2015,](requirements-for-your-environment/server-requirements.md)configure un nuevo entorno de Skype Empresarial Server 2015 y mueva usuarios allí. En el siguiente diagrama se muestra una introducción a este proceso para la actualización desde Lync Server 2010. 
  
![Diagrama de carril de natación que muestra los usuarios del grupo de servidores front-end principal de Lync Server que se mueven a Skype Empresarial Server 2015 y el grupo de servidores de Lync Server que se ha dado de baja.](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>Proceso de actualización local

 Actualice de Lync Server 2013 a Skype Empresarial Server 2015 con los pasos siguientes:
  
1. Copia de seguridad de todas las bases de datos antes de la actualización.
    
2. Asegúrese de que todos los servicios que se van a actualizar estén en estado de ejecución.
    
3. Actualice y publique el archivo de topología con el generador de topologías.
    
4. Detenga todos los servicios en todos los servidores front-end.
    
5. Instalar nuevos requisitos previos necesarios para Skype Empresarial Server.
    
6. En cada servidor front-end, inicie la actualización In-Place cliente.
    
7. Una vez completada la actualización, reinicie todos los servicios.
    
   - Para el grupo de servidores front-end, reinicie los servicios con el comando Start-CsPool.
    
   - Para servidores que no son front-end, use Start-CSWindowsService.
    
> [!NOTE]
>  Si no desea actualizar las bases de datos de archivado y supervisión existentes, quite la dependencia antes de actualizar la topología. Si desea crear nuevas bases de datos de archivado y supervisión, durante la actualización, puede crear un nuevo almacén de SQL y asociarlo con el grupo. Puede encontrar los pasos para hacerlo en el tema[Upgrade to Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md). > actualización local no admite alta disponibilidad ni recuperación ante desastres para Skype Empresarial Server. Para evitar interrumpir los servicios de los usuarios, use el método [Move Users (sin](upgrade.md#bkmk_MoveUsersMethod) tiempo de inactividad del usuario) para actualizar.> Durante el proceso de actualización, la réplica xds se coloca en la carpeta compartida local de la unidad de disco con más espacio libre. Si ese disco se quita más adelante, puede encontrarse con problemas como que los servicios no se inicien.
  
### <a name="upgrade-order"></a>Orden de actualización

Actualice la topología del interior al exterior. Actualice primero todos los grupos de servidores, después los servidores perimetrales y, por último, el grupo de servidores del Almacén de administración central (CMS). 
  
### <a name="kerberos-authentication-considerations"></a>Consideraciones de autenticación Kerberos

Si usa la autenticación Kerberos para servicios web, debe reasignar las cuentas Kerberos y restablecer la contraseña después de completar In-Place actualización. Para obtener información sobre cómo hacerlo, consulte [Configuración de la autenticación Kerberos](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-kerberos-authentication).
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>Compatibilidad con la coexistencia con Lync Server 2013 y Lync Server 2010
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Puede ejecutar Skype Empresarial Server 2015 en la misma topología que Lync Server 2013 o Lync Server 2010, pero no puede tener los tres en la misma topología.
  
Si tiene una coexistencia entre Lync Server 2010 y Lync Server 2013, se recomienda actualizar toda la topología a Lync Server 2013 y, a continuación, actualizar a Skype Empresarial Server 2015 mediante la actualización de In-Place. Para obtener más información, vea [Migración de Lync Server 2010 a Lync Server 2013](/previous-versions/office/lync-server-2013/migration-from-lync-server-2010-to-lync-server-2013).
  
Si la topología es principalmente Lync Server 2010, revierte los componentes de Lync Server 2013 a Lync Server 2010 antes de actualizar la topología a Skype Empresarial Server 2015. En este caso, pierde la ventaja de la actualización de In-Place y tiene una topología de coexistencia entre Lync Server 2010 y Skype Empresarial Server 2015.
  
En el siguiente diagrama se muestra la compatibilidad de coexistencia de Skype Empresarial Server 2015 con Lync Server 2013 y Lync Server 2010.
  
![Diagrama que muestra la compatibilidad de coexistencia para Skype Empresarial Server 2015 con Lync Server 2013 o Lync Server 2010.](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>Proceso de actualización con servidor y aplicación de sucursal con funciones de supervivencia existentes
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Skype Empresarial Server 2015 no admite una actualización In-Place de una aplicación de sucursal con funciones de supervivencia (SBA) o un servidor de sucursal con funciones de supervivencia (SBS).
  
Sin embargo, sí se admite la coexistencia de centros de datos de Skype Empresarial Server con Lync Server 2010 o Lync Server 2013 SBA/SBS. 
  
Al planear una actualización In-Place de un grupo de servidores front-end (FE) de Lync Server 2013 con una rama asociada, puede dejar a los usuarios existentes en el SBA/SBS de Lync Server 2013. Durante la actualización, los usuarios de SBA/SBS pasarán al modo de resistencia y volverán a la funcionalidad normal una vez completada la actualización. Para obtener más información sobre la experiencia de los usuarios durante el modo de resistencia, consulte Características de resistencia de sitios de sucursal [en Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-branch-site-resiliency-features).
  
Al migrar una topología de Lync Server 2010 a Skype Empresarial Server 2015, el SBA/SBS debe volver a agregarse a la topología, de forma similar a la migración a Lync Server 2013. Para obtener los pasos necesarios, lea [Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool](/previous-versions/office/lync-server-2013/lync-server-2013-connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool).
  
Para topologías de coexistencia de Lync Server 2010 y Lync Server 2013, alinee primero las recomendaciones realizadas en la sección "Compatibilidad para la coexistencia con Lync Server 2013 y Lync Server 2010".
  
## <a name="see-also"></a>Ver también
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

[Actualización a Skype Empresarial Server 2015](../deploy/upgrade-to-skype-for-business-server.md)
  
[Requisitos de entorno para Skype Empresarial Server 2015](requirements-for-your-environment/environmental-requirements.md)
  
[Requisitos del servidor para Skype Empresarial Server 2015](requirements-for-your-environment/server-requirements.md)