---
title: Alta disponibilidad del servidor back-end en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: Obtenga información sobre las opciones de alta disponibilidad del servidor back-end admitidas en Skype Empresarial Server, incluidos los grupos de disponibilidad AlwaysOn, las instancias del clúster de conmutación por error AlwaysOn, la creación de reflejo de la base de datos y SQL clústeres de conmutación por error.
ms.openlocfilehash: 5cc325b0726afab72581f679873fe454d8302dec5a478685c24e84b430a25017
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54318743"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a>Alta disponibilidad del servidor back-end en Skype Empresarial Server
 
Obtenga información sobre las opciones de alta disponibilidad del servidor back-end admitidas en Skype Empresarial Server, incluidos los grupos de disponibilidad AlwaysOn, las instancias del clúster de conmutación por error AlwaysOn, la creación de reflejo de la base de datos y SQL clústeres de conmutación por error.
  
Para mejorar la alta disponibilidad de los servidores back-end, tiene cuatro opciones:
  
- Creación de reflejos de base de datos
    
- Grupos de disponibilidad AlwaysOn
    
- Instancias del clúster de conmutación por error AlwaysOn (FCI)
    
- SQL clústeres de conmutación por error
    
El uso de una de estas soluciones es opcional, pero se recomienda mantener la continuidad empresarial de la organización. De lo contrario, tener un solo servidor de base de datos podría provocar la pérdida de datos Skype Empresarial Server datos. 
  
Puede configurar la creación de reflejos de la base de datos solo con el Generador de topologías. Para grupos de disponibilidad AlwaysOn, instancias de clúster de conmutación por error AlwaysOn o clústeres de conmutación por error de SQL, use SQL Server para crear la solución de alta disponibilidad y, a continuación, puede usar el Generador de topologías para asociarla a un grupo de servidores front-end.
  
Si usa la alta disponibilidad del servidor back-end en un grupo de servidores front-end que está emparejado con otro grupo de servidores front-end para la recuperación ante desastres, debe usar la misma solución back-end de alta disponibilidad en ambos grupos. 
  
## <a name="database-mirroring"></a>Creación de reflejos de base de datos

Skype Empresarial Server es compatible con la creación de reflejos con el siguiente software de base de datos:
  
- SQL Server 2019, tanto Enterprise Edition como Standard Edition

- SQL Server 2017, tanto Enterprise Edition como Standard Edition

- SQL Server 2016, tanto Enterprise Edition como Standard Edition

- SQL Server 2014, tanto Enterprise Edition como Standard Edition
    
- SQL Server 2012 SP2 y CU2, tanto Enterprise Edition como Standard Edition
    

> [!NOTE]
> SQL La creación de reflejos está disponible Skype Empresarial Server 2015, pero ya no se admite en Skype Empresarial Server 2019. Los grupos de disponibilidad AlwaysOn, las instancias de clúster de conmutación por error (FCI) AlwaysOn y los métodos de clústeres de conmutación por error SQL son las únicas opciones admitidas con Skype Empresarial Server 2019.
    
La creación de reflejo asincrónica de bases de datos no es compatible con la alta disponibilidad del servidor back-end en Skype Empresarial Server. En el resto de este documento, la creación de reflejo de la base de datos significa creación de reflejo sincrónica de la base de datos, a menos que se indique explícitamente lo contrario. 
  
Al implementar la creación de reflejos de bases de datos en un grupo de servidores front-end, todas las bases de datos de Skype Empresarial Server del grupo se reflejan, incluido el almacén de administración central, si se encuentra en este grupo, así como la base de datos de aplicaciones del grupo de respuesta y la base de datos de aplicaciones de estacionamiento de llamadas, si dichas aplicaciones se ejecutan en el grupo. 
  
Con la creación de reflejo de la base de datos, no es necesario usar el almacenamiento compartido para los servidores. Cada servidor guarda su copia de la base de datos en un almacenamiento local. 
  
Puede optar por implementar la creación de reflejos de la base de datos con o sin un testigo. Recomendamos utilizar un testigo porque esto permite que la conmutación por error del servidor back-end sea automática. De lo contrario, un administrador debe invocar manualmente la conmutación por error. Tenga en cuenta que incluso si se implementa un testigo, un administrador puede invocar manualmente la conmutación por error del servidor back-end, si fuera necesario.
  
Si utiliza un testigo, puede utilizar un único testigo para varios pares de servidores back-end. No existe una correspondencia estricta uno a uno entre testigos y pares de servidores back-end. Las implementaciones que utilizan un único testigo para varios pares de servidores back-end no son tan resistentes como las topologías con un testigo independiente para cada par de servidor back-end. 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a>Directrices para planear la creación de reflejos del servidor back-end

En general, la configuración de creación de reflejo de SQL entre los dos servidores back-end con un testigo requiere lo siguiente:
  
- La versión del servidor principal de SQL Server debe admitir SQL creación de reflejo.
    
- El servidor principal, reflejo y testigo (si se implementan) deben tener la misma versión de SQL Server. 
    
- El servidor principal y el reflejo deben tener la misma edición de SQL Server. El testigo puede tener una edición diferente.
    
Para SQL procedimientos recomendados en términos de lo que se admiten SQL versiones para un rol testigo, vea "Testigo de creación de reflejo de base de [datos"](/sql/database-engine/database-mirroring/database-mirroring-witness) en MSDN Library.
  
Antes de configurar la creación de reflejo del servidor, primero debe configurar los SQL de base de datos correctamente. Para obtener más información, vea "Configurar cuentas de inicio de sesión para la creación de reflejo de la base de datos o grupos de disponibilidad [AlwaysOn (SQL Server)"](/sql/database-engine/database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability).
  
Con el reflejo de SQL, el modo de recuperación de bases de datos siempre está configurado como **Completa**. Esto significa que deberá controlar atentamente el tamaño del registro de transacciones y crear copias de seguridad de los registros de transacciones periódicamente para evitar que los servidores back-end se queden sin espacio en disco. La frecuencia con que se deben crear copias de seguridad de los registros de transacciones depende de la tasa de crecimiento del registro, que, a su vez, depende de las transacciones de la base de datos producidas por las actividades del usuario en el grupo de servidores front-end. Le recomendamos que determine el crecimiento estimado del registro de transacciones que se necesitará para la carga de trabajo de su implementación de Lync, de modo que pueda realizar la planeación en consonancia. En los artículos siguientes encontrará información adicional sobre la administración del registro y la copia de seguridad de SQL:
  
> [!IMPORTANT]
> El uso del Generador de topologías o cmdlets para configurar y quitar la creación de reflejo de SQL solo se admite cuando los servidores primarios, reflejados y testigos (si se desea) pertenecen al mismo dominio. Si desea configurar la creación del reflejo de SQL entre servidores de dominios diferentes, consulte la documentación sobre SQL Server. 

> [!NOTE]
> SQL La creación de reflejos está disponible Skype Empresarial Server 2015, pero ya no se admite en Skype Empresarial Server 2019. Los grupos de disponibilidad AlwaysOn, las instancias de clúster de conmutación por error (FCI) AlwaysOn y SQL de clústeres de conmutación por error se prefieren Skype Empresarial Server 2019.
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a>Tiempo de recuperación para la conmutación por error automática del servidor back-end con creación de reflejo de la base de datos

Para la conmutación por error back-end automática con creación de reflejo de la base de datos, el objetivo de ingeniería para el objetivo de tiempo de recuperación (RTO) es de 5 minutos. Debido a la creación de reflejo sincrónica de la base de datos, no prevemos la pérdida de datos durante los errores del servidor back-end, excepto en raras ocasiones cuando los servidores front-end y el servidor back-end bajan simultáneamente mientras los datos se mueven entre los servidores. El destino de ingeniería para objetivo de punto de recuperación (RPO) es de 5 minutos.
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a>Experiencia del usuario durante un error del servidor back-end con creación de reflejo de la base de datos

La experiencia del usuario durante un error depende de la naturaleza del error y de la topología.
  
Si usa la creación de reflejo de la base de datos y tiene configurado un testigo y la entidad de seguridad falla, la conmutación por error del servidor back-end se produce automáticamente y rápidamente. Los usuarios activos no deberían notar muchas interrupciones en sus sesiones en curso.
  
Si no hay ningún testigo configurado, el administrador llevará algún tiempo invocar manualmente la conmutación por error. Durante ese tiempo, los usuarios activos pueden verse afectados. Continuarán sus sesiones con normalidad durante unos 30 minutos. Si el elemento principal aún no se restaura o un administrador no ha conmutado por error a la copia de seguridad, los usuarios cambian al modo de resistencia, lo que significa que no pueden realizar tareas que requieren un cambio persistente en Lync Server (como agregar un contacto).
  
Si tanto el servidor back-end principal como el de reflejo fallan o si se produce un error en uno de esos servidores y el testigo, el servidor back-end dejará de estar disponible (incluso si se trata del principal que sigue funcionando). En este caso, los usuarios activos se cambian al modo de resistencia después de algún tiempo.
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a>Grupos de disponibilidad AlwaysOn e instancias de clúster de conmutación por error AlwaysOn

Skype Empresarial Server admite grupos de disponibilidad AlwaysOn solo como activos/pasivos, no activos/activos. 
  
Para usar grupos de disponibilidad AlwaysOn o instancias de clúster de conmutación por error AlwaysOn, primero debe usar SQL Server para configurar y configurar la solución de alta disponibilidad. A continuación, puede usar el Generador de topologías para asociarlo a un grupo de servidores front-end.

Skype Empresarial Server admite AlwaysOn con el siguiente software de base de datos:

- SQL Server 2019 Enterprise Edition

- SQL Server 2019 Standard Edition limitaciones, vea la nota siguiente

- SQL Server 2017 Enterprise Edition

- SQL Server 2017 Standard Edition limitaciones, vea la nota siguiente

- SQL Server 2016 Enterprise Edition

- SQL Server 2016 Standard Edition con limitaciones, vea la nota siguiente

- SQL Server 2014 Enterprise Edition
    
- SQL Server 2012 SP2 y CU2 Enterprise Edition

> [!NOTE]
> SQL Server 2019, 2017 y 2016 son las únicas versiones admitidas por Skype Empresarial Server 2019.

> [!NOTE]
> Los grupos de  disponibilidad AlwaysOn no se admiten en las ediciones estándar de SQL 2016, 2017 y 2019, pero puede usar instancias de clúster de conmutación por error alwayson. Consulta [Ediciones y características compatibles de SQL Server 2016](/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017) para obtener más información.
  
> [!IMPORTANT]
> Los nombres de instancia de varias instancias del grupo de disponibilidad AlwaysOn deben ser los mismos. 
  
Para ver los pasos para implementar grupos de disponibilidad AlwaysOn, vea [Deploy an AlwaysOn Availability Group on a Back End Server in Skype Empresarial Server](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md).
  
## <a name="sql-server-failover-clustering"></a>SQL Server Clústeres de conmutación por error

Skype Empresarial Server admite SQL Server clústeres de conmutación por error con el siguiente software de base de datos:
  
- SQL Server 2019, tanto Enterprise Edition como Standard Edition

- SQL Server 2017, tanto Enterprise Edition como Standard Edition

- SQL Server 2016, tanto Enterprise Edition como Standard Edition

- SQL Server 2014, tanto Enterprise Edition como Standard Edition
    
- SQL Server 2012 SP2 y CU2, tanto Enterprise Edition como Standard Edition

Para usar SQL clústeres de conmutación por error, primero debe configurar el clúster de SQL Server antes de implementar el grupo de servidores front-end. Para obtener instrucciones de configuración y procedimientos recomendados para clústeres de conmutación por error SQL Server 2012, vea [https://technet.microsoft.com/library/hh231721.aspx](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation) .

> [!NOTE]
> SQL Server 2019, 2017 y SQL Server 2016 son las únicas versiones admitidas por Skype Empresarial Server 2019.
    
Para usar SQL clústeres de conmutación por error, primero debe configurar el clúster de SQL Server antes de implementar el grupo de servidores front-end. Para obtener instrucciones de configuración y procedimientos recomendados para clústeres de conmutación por error SQL Server 2014 y 2016, vea [https://technet.microsoft.com/library/hh231721.aspx](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation) . Para clústeres de conmutación por error SQL Server 2008, vea [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](/previous-versions/sql/sql-server-2008-r2/ms189134(v=sql.105)) .
  
Cuando instale SQL Server, instale también SQL Server Management Studio para administrar las ubicaciones de la base de datos y las ubicaciones de archivo de registro. SQL Server Management Studio se instala como componente adicional al instalar SQL Server.
