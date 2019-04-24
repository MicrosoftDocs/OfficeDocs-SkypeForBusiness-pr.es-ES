---
title: Back-End alta disponibilidad del servidor en Skype para Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: Obtenga información sobre las opciones de alta disponibilidad de servidor Back-End admitidas en Skype para Business Server, incluidos los grupos de disponibilidad AlwaysOn, las instancias de clúster de conmutación por error de AlwaysOn, la creación de reflejo de la base de datos y agrupación en clústeres de conmutación por error SQL.
ms.openlocfilehash: 5f95ea1a1a856db945e1d0fac5683b1fb8c4c02e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214106"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a>Back-End alta disponibilidad del servidor en Skype para Business Server
 
Obtenga información sobre las opciones de alta disponibilidad de servidor Back-End admitidas en Skype para Business Server, incluidos los grupos de disponibilidad AlwaysOn, las instancias de clúster de conmutación por error de AlwaysOn, la creación de reflejo de la base de datos y agrupación en clústeres de conmutación por error SQL.
  
Tiene cuatro opciones para mejorar la alta disponibilidad de sus servidores back-end:
  
- Creación de reflejo de la base de datos
    
- Grupos de disponibilidad AlwaysOn
    
- Instancias de clúster de conmutación por error de AlwaysOn (FCI)
    
- Clústeres de conmutación por error de SQL
    
El uso de una u otra solución es opcional, pero recomendamos mantener la continuidad empresarial de la organización. De lo contrario, la necesidad de un servidor de base de datos única vaya hacia abajo podría provocar la pérdida de Skype significativo para los datos de Business Server. 
  
Puede establecer la creación de reflejos de base de datos mediante el generador de topología sólo. Para grupos de disponibilidad AlwaysOn, las instancias de clúster de conmutación por error AlwaysOn o agrupación en clústeres de conmutación por error SQL, utilice SQL Server para crear la solución de alta disponibilidad, a continuación, puede usar el generador de topología para asociarlo a un grupo de servidores Front-End.
  
Si usa una alta disponibilidad de servidor Back-End en un grupo de servidores Front-End que se empareja con otro grupo de servidores Front-End para la recuperación ante desastres, debe usar la misma solución de alta disponibilidad de Back-End en ambos grupos. 
  
## <a name="database-mirroring"></a>Creación de reflejo de la base de datos

Skype para Business Server admite la creación de reflejos con el software de base de datos siguientes:
  
- SQL Server 2016, Enterprise Edition y Standard Edition

- SQL Server Enterprise Edition y Standard Edition de 2014
    
- Service Pack 2 SQL Server 2012 y CU2, Enterprise Edition y Standard Edition
    

> [!NOTE]
> SQL Server 2016 es la única versión compatible con Skype para Business Server 2019.
    
La creación de reflejo de base de datos asincrónica no se admite para alta disponibilidad de servidor Back-End en Skype para Business Server. En lo que resta de este documento, la creación de reflejo de la base de datos implica la creación de reflejo de la base de datos sincrónica, a menos que se indique lo contrario. 
  
Al implementar la creación de reflejo de base de datos en un grupo de servidores Front-End, se reflejan Skype todas las bases de datos de Business Server en el grupo de servidores, incluido el almacén de Administración Central, si se encuentra en este grupo de servidores, así como la base de datos de aplicación de grupo de respuesta y estacionamiento de llamadas base de datos de aplicación, si dichas aplicaciones se ejecutan en el grupo de servidores. 
  
Con la creación de reflejo de la base de datos, no es necesario usar el almacenamiento compartido para los servidores. Cada servidor guarda su copia de la base de datos en un almacenamiento local. 
  
Puede optar por implementar una creación de reflejo de la base de datos con o sin un testigo. Recomendamos usar un testigo, porque esto permite que la conmutación por error del servidor back-end sea automática. De lo contrario, un administrador tendrá que invocar manualmente la conmutación por error. Tenga en cuenta que, incluso si se implementa un testigo, un administrador puede invocar manualmente la conmutación por error del servidor back-end, si fuera necesario.
  
Si usa un testigo, puede usar un único testigo para varios pares de servidores back-end. No existe una correspondencia estricta uno a uno entre testigos y pares de servidores back-end. Las implementaciones en las que se emplea un único testigo para varios pares de servidores back-end no son tan resistentes como las topologías con un testigo independiente para cada par de servidor back-end. 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a>Instrucciones para planificar la creación de reflejo del servidor back-end

En general, la configuración de creación de reflejo de SQL entre los dos servidores back-end con un testigo requiere lo siguiente:
  
- Versión del servidor principal de SQL Server debe admitir la creación de reflejos de SQL.
    
- El servidor principal, el reflejo y el testigo (si se implementan) necesitan tener la misma versión de SQL Server. 
    
- El servidor principal y el reflejo necesitan tener la misma edición de SQL Server. El testigo puede tener una edición diferente.
    
Procedimientos recomendados de SQL en términos de qué versiones SQL son compatibles para un rol de testigo, consulte ["testigo de creación de reflejo de base de datos"](https://go.microsoft.com/fwlink/p/?LinkId=247345) en MSDN Library.
  
Para configurar la creación de reflejo del servidor, es necesario que primero configure los permisos de la base de datos de SQL correctamente. Para obtener información detallada, vea ["Configurar las cuentas de inicio de sesión para la creación de reflejos de base de datos o grupos de disponibilidad AlwaysOn (SQL Server)"](https://go.microsoft.com/fwlink/p/?LinkId=268454).
  
Con el reflejo de SQL, el modo de recuperación de bases de datos siempre está configurado como **Completa**. Esto significa que es preciso controlar atentamente el tamaño del registro de transacciones y crear copias de seguridad de los registros de transacciones periódicamente para evitar que los servidores back-end se queden sin espacio en disco. La frecuencia con que se necesitan crear copias de seguridad de los registros de transacciones depende de la tasa de crecimiento del registro, que, a su vez, depende de las transacciones de la base de datos producidas por las actividades del usuario en el grupo de servidores front-end. Recomendamos que determine el crecimiento estimado del registro de transacciones para la carga de trabajo de la implementación de Skype Empresarial, de modo que pueda realizar la planeación en consonancia. En los artículos siguientes encontrará información adicional sobre la administración del registro y la copia de seguridad de SQL:
  
> [!IMPORTANT]
> La creación de reflejos se admite el uso de Topology Builder o cmdlets para configurar y quitar SQL sólo cuando la principal, reflejado y servidores testigo (si así lo desea) pertenecen al mismo dominio. Si desea configurar la creación del reflejo de SQL entre servidores de dominios diferentes, consulte la documentación de SQL Server. 

> [!NOTE]
> La creación de reflejos de SQL está disponible en Skype para Business Server 2015, pero ya no se admite en Skype para Business Server 2019. Los métodos de agrupación en clústeres de conmutación por error de grupos de disponibilidad AlwaysOn, instancias de clúster de conmutación por error (FCI) AlwaysOn y SQL son preferidos con Skype para Business Server 2019.
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a>Tiempo de recuperación de conmutación por error automática de servidor back-end con la creación de reflejo

Para la conmutación por error automática de servidores back-end con la creación de reflejos, el objetivo de ingeniería para el objetivo de tiempo de recuperación (RTO) es de 5 minutos. Debido a la creación de reflejos sincrónica, no prevemos pérdida de datos durante los errores en el servidor back-end, excepto en raras ocasiones, cuando tanto los servidores front-end como los servidores back-end dejan de funcionar simultáneamente mientras se mueven datos entre los servidores. El objetivo de ingeniería para el objetivo de punto de recuperación (RPO) es de 5 minutos.
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a>Experiencia del usuario durante un error de servidor back-end con la creación de reflejo

La experiencia del usuario durante un error depende de la naturaleza del error y de la topología.
  
Si usa la creación de reflejo de bases de datos y tiene un testigo configurado y se produce un error en la entidad principal, la conmutación por error del servidor back-end se produce de forma rápida y automática. Los usuarios activos no tendrían que notar muchas interrupciones en sus sesiones en curso.
  
Si no hay ningún testigo configurado, tomará algún tiempo que el administrador invoque manualmente la conmutación por error. Durante ese tiempo, los usuarios activos probablemente lo notarán. Continuarán con sus sesiones normalmente durante unos 30 minutos. Si la principal aún no se ha restaurado, o un administrador ha no conmuta por error a la copia de seguridad, a continuación, los usuarios se cambian a modo de resistencia, lo que significa que se hayan definido no se puede realizar las tareas que requieren un cambio persistente en Lync Server (por ejemplo, para agregar un contacto).
  
Si tanto el servidor back-end principal como el de reflejo fallan o si se produce un error en uno de esos servidores y el testigo, el servidor back-end dejará de estar disponible (incluso si se trata del principal que sigue funcionando). En este caso, los usuarios activos se cambian al modo de resistencia después de algún tiempo.
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a>Grupos de disponibilidad AlwaysOn e instancias de clústeres de conmutación por error AlwaysOn

Grupos de disponibilidad AlwaysOn y las instancias de clúster de conmutación por error AlwaysOn se admiten sólo en SQL Server 2014 Enterprise Edition y Enterprise Edition de SQL Server 2012. Skype para Business Server admite grupos de disponibilidad AlwaysOn sólo como activo/pasivo, no activo/activo. 
  
Para usar grupos de disponibilidad AlwaysOn o las instancias de clúster de conmutación por error de AlwaysOn, primero utilizar SQL Server para instalar y configurar la solución de alta disponibilidad. A continuación, puede usar el generador de topología para asociarlo a un grupo de servidores Front-End.
  
> [!IMPORTANT]
> Los nombres de instancia para varias instancias de grupo de disponibilidad AlwaysOn deben ser el mismo. 
  
Para ver los pasos para la implementación de grupos de disponibilidad AlwaysOn, vea [implementar un grupo de disponibilidad AlwaysOn en un servidor Back-End en Skype para Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md).
  
## <a name="sql-server-failover-clustering"></a>Clústeres de conmutación por error de SQL Server

Skype para Business Server admite clústeres con el siguiente software de base de datos de conmutación por error de SQL Server:
  
- SQL Server 2017, Enterprise Edition y Standard Edition

- SQL Server 2016, Enterprise Edition y Standard Edition

- SQL Server Enterprise Edition y Standard Edition de 2014
    
- Service Pack 2 SQL Server 2012 y CU2, Enterprise Edition y Standard Edition

Para usar la agrupación en clústeres de conmutación por error SQL, primero debe configurar y configurar el clúster de SQL Server antes de implementar el grupo de servidores Front-End. Para obtener instrucciones de instalación para conmutación por error de SQL Server 2012 y procedimientos recomendados, consulte [https://technet.microsoft.com/en-us/library/hh231721.aspx](https://technet.microsoft.com/en-us/library/hh231721.aspx).

> [!NOTE]
> 2017 de SQL Server y SQL Server 2016 son las únicas versiones compatibles con Skype para Business Server 2019.
    
Para usar la agrupación en clústeres de conmutación por error SQL, primero debe configurar y configurar el clúster de SQL Server antes de implementar el grupo de servidores Front-End. Para obtener instrucciones de instalación para conmutación por error de SQL Server 2014 y 2016 y procedimientos recomendados, consulte [https://technet.microsoft.com/en-us/library/hh231721.aspx](https://technet.microsoft.com/en-us/library/hh231721.aspx). Para la conmutación por error de agrupación en clústeres de SQL Server 2008, consulte [https://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/en-us/library/ms189134%28v=sql.105%29.aspx).
  
Al instalar SQL Server, es preciso instalar también SQL Server Management Studio para administrar las ubicaciones de la base de datos y de los archivos de registro. SQL Server Management Studio se instala como un componente opcional al instalar SQL Server.
  

