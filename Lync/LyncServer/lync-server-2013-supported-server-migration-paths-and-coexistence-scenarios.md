---
title: "Lync Server 2013: Rutas de migración de servidor compat. y escenarios de coexistencia"
TOCTitle: Vías de migración de servidor compatibles y escenarios de coexistencia
ms:assetid: 2a6a730f-7f80-45f9-9540-3edfdaa265fb
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425764(v=OCS.15)
ms:contentKeyID: 48274754
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vías de migración de servidor compatibles y escenarios de coexistencia en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-16_

Lync Server 2013 admite la migración desde los siguientes entornos:

  - Microsoft Lync Server 2010

  - Microsoft Office Communications Server 2007 R2

No se admite la migración de un entorno que ejecuta ambas de estas versiones anteriores. No se admite la migración de versiones anteriores, como Microsoft Office Communications Server 2007 o Live Communications Server 2005. Si su implementación anterior incluía Chat en grupo, es necesario migrarla de manera independiente.

## Métodos de migración

Se admite la migración de todas las topologías de Lync Server y funciones de servidor. Puede migrar de una topología a otra, incluso desde un servidor Standard Edition a un servidor Enterprise Edition en una configuración consolidada.

Lync Server 2013 solo admite el siguiente método de migración:

  **Migración en paralelo.** En la migración en paralelo, Lync Server 2013 se implementa junto con una implementación de Microsoft Lync Server 2010 o Office Communications Server 2007 R2 existente y después se transfieren las operaciones a los nuevos servidores y se mueven los usuarios a Lync Server 2013. Este método requiere plataformas de servidores adicionales, tanto hardware como software, durante la migración. Además, los nombres del sistema y de los grupos de servidores son diferentes en la nueva configuración. Si fuera necesario volver a la versión anterior, puede transferir las operaciones a los servidores anteriores.

No se admite la migración entre bosques de Servicios de dominio de Active Directory.

La vía de migración recomendada se basa en fases. Para más información sobre la migración desde una versión anterior, incluida la fase correspondiente de la implementación de componentes, consulte los siguientes temas en la documentación sobre migración:

  - [Migrar Lync Server 2010 a Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [Migrar de Office Communications Server 2007 R2 a Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [Migración del chat de grupo de Lync Server 2010 o el chat de grupo de Office Communications Server 2007 R2 al servidor de chat persistente de Lync Server 2013](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

## Escenarios de coexistencia

Lync Server 2013 puede coexistir con componentes de una implementación de Lync Server 2010 o Office Communications Server 2007 R2. No se admite la implementación simultánea de Lync Server 2013 con Lync Server 2010 y Office Communications Server 2007 R2 (implementación simultánea de las tres versiones).

Durante una migración por fases en la que una implementación anterior de Lync Server 2013 o Office Communications Server 2007 R2 coexiste temporalmente con la nueva implementación de Lync Server 2010, la compatibilidad con el enrutamiento de versiones mixtas es limitada. Para más información, consulte la documentación sobre migración.

Debe utilizar equipos distintos e independientes que ejecuten Microsoft SQL Server 2008 R2 o Microsoft SQL Server 2012 para sus instancias de bases de datos de Lync Server 2013. No puede utilizar la misma instancia de SQL Server para un grupo de servidores front-end de Lync Server 2013 que utiliza para un Lync Server 2010 o grupo de servidores front-end de Office Communications Server 2007 R2. Si define y configura Lync Server 2013 en Generador de topologías para una implementación que ya tiene Lync Server 2010 o Office Communications Server 2007 R2 implementado, Generador de topologías no le permitirá definir una instancia de un Lync Server 2013 que ya esté en uso en la topología.

Generador de topologías mostrará el siguiente mensaje para informarle de este problema: "El SQL Server \[FQDN del servidor\] ya contiene un rol de hospedaje de instancia de SQL 'Almacenamiento de usuarios'".


> [!NOTE]
> Si tiene pensado implementar roles de servidor nuevos en su implementación de Lync Server 2013, primero es necesario actualizar la implementación existente tal y como se describe en la documentación sobre migración e implementación y después implementar los nuevos roles de servidor, como se describe en la documentación sobre planeación e implementación. Si migra una versión anterior de Chat en grupo, mígrela en último lugar, después de completar el proceso para migrar todos los demás componentes de Lync Server 2010 o Office Communications Server 2007 R2.



Si desea conocer los requisitos de coexistencia y otros detalles sobre la coexistencia y migración de Lync Server 2010 o Office Communications Server 2007 R2 y los componentes de Lync Server 2013, consulte [Migrar Lync Server 2010 a Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) y [Migrar de Office Communications Server 2007 R2 a Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) en la documentación sobre migración. Para obtener información sobre la compatibilidad de versiones mixtas en clientes, consulte [Clientes admitidos de implementaciones anteriores en Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).

