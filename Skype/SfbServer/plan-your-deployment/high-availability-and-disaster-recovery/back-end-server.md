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
description: Obtenga información sobre las opciones de alta disponibilidad del servidor back-end admitidas en Skype Empresarial Server, incluidos los grupos de disponibilidad AlwaysOn, las instancias de clúster de conmutación por error de AlwaysOn, la creación de reflejo de la base de datos y los clústeres de conmutación por error SQL servidor.
ms.openlocfilehash: bbb55ded0d5ce1127f5dcab829907c533cc6316e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802930"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a>Alta disponibilidad del servidor back-end en Skype Empresarial Server
 
Obtenga información sobre las opciones de alta disponibilidad del servidor back-end admitidas en Skype Empresarial Server, incluidos los grupos de disponibilidad AlwaysOn, las instancias de clúster de conmutación por error de AlwaysOn, la creación de reflejo de la base de datos y los clústeres de conmutación por error SQL servidor.
  
Para mejorar la alta disponibilidad de los servidores back-end, tiene cuatro opciones:
  
- Creación de reflejos de base de datos
    
- Grupos de disponibilidad AlwaysOn
    
- Instancias de clúster de conmutación por error (FCI) AlwaysOn
    
- SQL clústeres de conmutación por error
    
El uso de una de estas soluciones es opcional, pero se recomienda mantener la continuidad empresarial de la organización. De lo contrario, tener un único servidor de base de datos podría causar la pérdida de datos importantes de Skype Empresarial Server. 
  
Puede configurar la creación de reflejos de la base de datos solo mediante el Generador de topologías. Para los grupos de disponibilidad AlwaysOn, las instancias de clúster de conmutación por error de AlwaysOn o los clústeres de conmutación por error de SQL, se usa SQL Server para crear la solución de alta disponibilidad y, a continuación, se puede usar el Generador de topologías para asociarla a un grupo de servidores front-end.
  
Si usa alta disponibilidad del servidor back-end en un grupo de servidores front-end que está emparejado con otro grupo de servidores front-end para la recuperación ante desastres, debe usar la misma solución de alta disponibilidad back-end en ambos grupos. 
  
## <a name="database-mirroring"></a>Creación de reflejos de base de datos

Skype Empresarial Server admite la creación de reflejos con el siguiente software de base de datos:
  
- SQL Server 2019, Enterprise Edition y Standard Edition

- SQL Server 2017, Enterprise Edition y Standard Edition

- SQL Server 2016, Enterprise Edition y Standard Edition

- SQL Server 2014, Enterprise Edition y Standard Edition
    
- SQL Server 2012 SP2 y CU2, Enterprise Edition y Standard Edition
    

> [!NOTE]
> SQL mirroring está disponible en Skype Empresarial Server 2015, pero ya no se admite en Skype Empresarial Server 2019. Los grupos de disponibilidad AlwaysOn, las instancias de clúster de conmutación por error (FCI) AlwaysOn y los métodos de clústeres de conmutación por error de SQL son las únicas opciones admitidas con Skype Empresarial Server 2019.
    
La creación de reflejo asincrónica de la base de datos no es compatible con la alta disponibilidad del servidor back-end en Skype Empresarial Server. En el resto de este documento, la creación de reflejo de la base de datos significa creación de reflejo de base de datos sincrónica, a menos que se indique explícitamente lo contrario. 
  
Al implementar la creación de reflejo de la base de datos en un grupo de servidores front-end, todas las bases de datos de Skype Empresarial Server del grupo se reflejan, incluido el almacén de administración central, si se encuentra en este grupo de servidores, así como la base de datos de aplicaciones de grupo de respuesta y la base de datos de aplicación estacionamiento de llamadas, si dichas aplicaciones se ejecutan en el grupo. 
  
Con la creación de reflejo de la base de datos, no es necesario usar el almacenamiento compartido para los servidores. Cada servidor guarda su copia de la base de datos en un almacenamiento local. 
  
Puede optar por implementar la creación de reflejo de la base de datos con o sin un testigo. Recomendamos utilizar un testigo porque esto permite que la conmutación por error del servidor back-end sea automática. De lo contrario, un administrador debe invocar manualmente la conmutación por error. Tenga en cuenta que incluso si se implementa un testigo, un administrador puede invocar manualmente la conmutación por error del servidor back-end, si fuera necesario.
  
Si utiliza un testigo, puede utilizar un único testigo para varios pares de servidores back-end. No existe una correspondencia estricta uno a uno entre testigos y pares de servidores back-end. Las implementaciones que utilizan un único testigo para varios pares de servidores back-end no son tan resistentes como las topologías con un testigo independiente para cada par de servidor back-end. 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a>Directrices para planear la creación de reflejos del servidor back-end

En general, la configuración de creación de reflejo de SQL entre los dos servidores back-end con un testigo requiere lo siguiente:
  
- La versión del servidor principal de SQL Server debe admitir SQL creación de reflejos.
    
- El servidor principal, reflejo y testigo (si se implementan) deben tener la misma versión de SQL Server. 
    
- El servidor principal y el reflejo deben tener la misma edición de SQL Server. El testigo puede tener una edición diferente.
    
Para SQL procedimientos recomendados en lo que se SQL versiones de SQL para un rol testigo, vea "Testigo de creación de reflejo de la base de  [datos"](https://go.microsoft.com/fwlink/p/?LinkId=247345) en MSDN Library.
  
Antes de configurar la creación de reflejos del servidor, primero debe configurar los SQL de base de datos correctamente. Para obtener más información, vea "Configurar cuentas de inicio de sesión para la creación de reflejo de la base de datos o grupos de [disponibilidad AlwaysOn (SQL Server)".](https://go.microsoft.com/fwlink/p/?LinkId=268454)
  
Con el reflejo de SQL, el modo de recuperación de bases de datos siempre está configurado como **Completa**. Esto significa que deberá controlar atentamente el tamaño del registro de transacciones y crear copias de seguridad de los registros de transacciones periódicamente para evitar que los servidores back-end se queden sin espacio en disco. La frecuencia con que se deben crear copias de seguridad de los registros de transacciones depende de la tasa de crecimiento del registro, que, a su vez, depende de las transacciones de la base de datos producidas por las actividades del usuario en el grupo de servidores front-end. Le recomendamos que determine el crecimiento estimado del registro de transacciones que se necesitará para la carga de trabajo de su implementación de Lync, de modo que pueda realizar la planeación en consonancia. En los artículos siguientes encontrará información adicional sobre la administración del registro y la copia de seguridad de SQL:
  
> [!IMPORTANT]
> El uso del Generador de topologías o cmdlets para configurar y quitar la creación de reflejos de SQL solo se admite cuando los servidores principales, reflejados y testigos (si lo desea) pertenecen al mismo dominio. Si desea configurar la creación del reflejo de SQL entre servidores de dominios diferentes, consulte la documentación sobre SQL Server. 

> [!NOTE]
> SQL mirroring está disponible en Skype Empresarial Server 2015, pero ya no se admite en Skype Empresarial Server 2019. Los grupos de disponibilidad AlwaysOn, las instancias de clúster de conmutación por error (FCI) AlwaysOn y SQL de clústeres de conmutación por error son preferidos con Skype Empresarial Server 2019.
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a>Tiempo de recuperación para la conmutación por error automática del servidor back-end con creación de reflejo de la base de datos

Para la conmutación por error back-end automática con creación de reflejo de la base de datos, el objetivo de ingeniería para el objetivo de tiempo de recuperación (RTO) es de 5 minutos. Debido a la creación de reflejo de la base de datos sincrónica, no prevemos la pérdida de datos durante los errores del servidor back-end, excepto en raras ocasiones cuando los servidores front-end y el servidor back-end se desplazan simultáneamente mientras los datos se mueven entre los servidores. El destino de ingeniería para objetivo de punto de recuperación (RPO) es de 5 minutos.
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a>Experiencia del usuario durante un error en el servidor back-end con la creación de reflejo de la base de datos

La experiencia del usuario durante un error depende de la naturaleza del error y de la topología.
  
Si usa la creación de reflejo de la base de datos y tiene configurado un testigo y se produce un error en la entidad de seguridad, la conmutación por error del servidor back-end se produce automáticamente y rápidamente. Los usuarios activos no deberían notar muchas interrupciones en sus sesiones en curso.
  
Si no hay ningún testigo configurado, el administrador llevará algún tiempo invocar manualmente la conmutación por error. Durante ese tiempo, los usuarios activos pueden verse afectados. Continuarán sus sesiones de forma normal durante unos 30 minutos. Si el principal aún no se restaura o un administrador no ha conmutado por error a la copia de seguridad, los usuarios se cambian al modo de resistencia, lo que significa que no pueden realizar tareas que requieran un cambio persistente en Lync Server (como agregar un contacto).
  
Si tanto el servidor back-end principal como el de reflejo fallan o si se produce un error en uno de esos servidores y el testigo, el servidor back-end dejará de estar disponible (incluso si se trata del principal que sigue funcionando). En este caso, los usuarios activos se cambian al modo de resistencia después de algún tiempo.
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a>Grupos de disponibilidad AlwaysOn e instancias de clúster de conmutación por error AlwaysOn

Skype Empresarial Server solo admite grupos de disponibilidad AlwaysOn como activos/pasivos, no activos/activos. 
  
Para usar grupos de disponibilidad AlwaysOn o instancias de clúster de conmutación por error AlwaysOn, primero debe usar SQL Server para configurar la solución de alta disponibilidad. A continuación, puede usar el Generador de topologías para asociarlo a un grupo de servidores front-end.

Skype Empresarial Server admite AlwaysOn con el siguiente software de base de datos:

- SQL Server 2019 Enterprise Edition

- SQL Server 2019 Standard Edition con limitaciones, consulta la nota siguiente

- SQL Server 2017 Enterprise Edition

- SQL Server 2017 Standard Edition con limitaciones, consulta la nota siguiente

- SQL Server 2016 Enterprise Edition

- SQL Server 2016 Standard Edition con limitaciones, consulta la nota siguiente

- SQL Server 2014 Enterprise Edition
    
- SQL Server 2012 SP2 y CU2 Enterprise Edition

> [!NOTE]
> SQL Server 2019, 2017 y 2016 son las únicas versiones compatibles con Skype Empresarial Server 2019.

> [!NOTE]
> Los grupos de  disponibilidad AlwaysOn no se admiten en las ediciones standard de SQL 2016, 2017 y 2019, pero puede usar instancias de clúster de conmutación por error de AlwaysOn. Vea [las ediciones y las características compatibles de SQL Server 2016](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017) para obtener más información.
  
> [!IMPORTANT]
> Los nombres de instancia para varias instancias del grupo de disponibilidad AlwaysOn deben ser los mismos. 
  
Para ver los pasos para implementar grupos de disponibilidad AlwaysOn, consulte Implementar un grupo de disponibilidad AlwaysOn en un servidor [back-end en Skype Empresarial Server.](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md)
  
## <a name="sql-server-failover-clustering"></a>SQL Server clústeres de conmutación por error

Skype Empresarial Server admite clústeres SQL Server conmutación por error con el siguiente software de base de datos:
  
- SQL Server 2019, Enterprise Edition y Standard Edition

- SQL Server 2017, Enterprise Edition y Standard Edition

- SQL Server 2016, Enterprise Edition y Standard Edition

- SQL Server 2014, Enterprise Edition y Standard Edition
    
- SQL Server 2012 SP2 y CU2, Enterprise Edition y Standard Edition

Para usar SQL clústeres de conmutación por error, primero debe configurar el clúster de SQL Server antes de implementar el grupo de servidores front-end. Para obtener procedimientos recomendados e instrucciones de configuración para clústeres de conmutación por error SQL Server 2012, vea [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx) .

> [!NOTE]
> SQL Server 2019, 2017 y SQL Server 2016 son las únicas versiones compatibles con Skype Empresarial Server 2019.
    
Para usar SQL clústeres de conmutación por error, primero debe configurar el clúster de SQL Server antes de implementar el grupo de servidores front-end. Para obtener procedimientos recomendados e instrucciones de configuración para clústeres de conmutación por error SQL Server 2014 y 2016, vea [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx) . Para clústeres de conmutación por error SQL Server 2008, vea [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx) .
  
Cuando instale SQL Server, instale también SQL Server Management Studio para administrar las ubicaciones de la base de datos y las ubicaciones de archivo de registro. SQL Server Management Studio se instala como componente adicional al instalar SQL Server.
  
