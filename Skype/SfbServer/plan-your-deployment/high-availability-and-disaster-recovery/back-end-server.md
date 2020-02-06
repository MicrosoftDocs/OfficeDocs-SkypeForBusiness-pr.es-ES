---
title: Servidor back-end de alta disponibilidad en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: Obtenga más información sobre las opciones de alta disponibilidad del servidor de back-end admitidas en Skype empresarial Server, incluidos los grupos de disponibilidad AlwaysOn, las instancias de clúster de conmutación por error de AlwaysOn, la creación de reflejo de base de datos y la conmutación por error de SQL
ms.openlocfilehash: a0aeb53aea0ee2eab25875de0fddbfd0fc26d90a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815958"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a>Servidor back-end de alta disponibilidad en Skype empresarial Server
 
Obtenga más información sobre las opciones de alta disponibilidad del servidor de back-end admitidas en Skype empresarial Server, incluidos los grupos de disponibilidad AlwaysOn, las instancias de clúster de conmutación por error de AlwaysOn, la creación de reflejo de base de datos y la conmutación por error de SQL
  
Tiene cuatro opciones para mejorar la alta disponibilidad de sus servidores back-end:
  
- Creación de reflejo de la base de datos
    
- Grupos de disponibilidad AlwaysOn
    
- Instancias de clúster de conmutación por error de AlwaysOn (FCI)
    
- Clústeres de conmutación por error de SQL
    
El uso de una u otra solución es opcional, pero recomendamos mantener la continuidad empresarial de la organización. De lo contrario, el hecho de que un único servidor de base de datos se desconecte podría causar la pérdida de datos importantes de Skype empresarial Server. 
  
Puede configurar la creación de reflejo de base de datos solo con el generador de topologías. Para los grupos de disponibilidad AlwaysOn, las instancias de clúster de conmutación por error AlwaysOn, o el clúster de conmutación por error de SQL, use SQL Server para crear la solución de alta disponibilidad y, después, puede usar el generador de topología para asociarlo con un grupo de servidores front-end.
  
Si usa la alta disponibilidad del servidor back end en un grupo de servidores front-end que está emparejado con otro grupo de servidores front-end para la recuperación ante desastres, debe usar la solución de alta disponibilidad de back-end en ambos grupos. 
  
## <a name="database-mirroring"></a>Creación de reflejo de la base de datos

Skype empresarial Server admite el reflejo con el siguiente software de base de datos:
  
- SQL Server 2019, Enterprise Edition y Standard Edition

- SQL Server 2017, Enterprise Edition y Standard Edition

- SQL Server 2016, Enterprise Edition y Standard Edition

- SQL Server 2014, Enterprise Edition y Standard Edition
    
- SQL Server 2012 SP2 y CU2, tanto Enterprise Edition como Standard Edition
    

> [!NOTE]
> La creación de reflejos de SQL está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019. Los grupos de disponibilidad AlwaysOn, las instancias de clúster de conmutación por error (FCI) AlwaysOn, y los métodos de clúster de conmutación por error de SQL son preferidos con Skype empresarial Server 2019.
    
El reflejo de la base de datos asincrónica no es compatible con la alta disponibilidad del servidor back-end en Skype empresarial Server. En lo que resta de este documento, la creación de reflejo de la base de datos implica la creación de reflejo de la base de datos sincrónica, a menos que se indique lo contrario. 
  
Al implementar el reflejo de base de datos en un grupo de servidores front-end, todas las bases de datos de Skype empresarial Server del grupo están reflejadas, incluido el almacén central de administración, si se encuentra en este grupo, así como la base de datos de aplicación de grupo de respuesta y el parque de llamadas base de datos de la aplicación, si dichas aplicaciones se ejecutan en el grupo. 
  
Con la creación de reflejo de la base de datos, no es necesario usar el almacenamiento compartido para los servidores. Cada servidor guarda su copia de la base de datos en un almacenamiento local. 
  
Puede optar por implementar una creación de reflejo de la base de datos con o sin un testigo. Recomendamos usar un testigo, porque esto permite que la conmutación por error del servidor back-end sea automática. De lo contrario, un administrador tendrá que invocar manualmente la conmutación por error. Tenga en cuenta que, incluso si se implementa un testigo, un administrador puede invocar manualmente la conmutación por error del servidor back-end, si fuera necesario.
  
Si usa un testigo, puede usar un único testigo para varios pares de servidores back-end. No existe una correspondencia estricta uno a uno entre testigos y pares de servidores back-end. Las implementaciones en las que se emplea un único testigo para varios pares de servidores back-end no son tan resistentes como las topologías con un testigo independiente para cada par de servidor back-end. 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a>Instrucciones para planificar la creación de reflejo del servidor back-end

En general, la configuración de creación de reflejo de SQL entre los dos servidores back-end con un testigo requiere lo siguiente:
  
- La versión del servidor principal de SQL Server debe ser compatible con el reflejo SQL.
    
- El servidor principal, el reflejo y el testigo (si se implementan) necesitan tener la misma versión de SQL Server. 
    
- El servidor principal y el reflejo necesitan tener la misma edición de SQL Server. El testigo puede tener una edición diferente.
    
Para obtener los procedimientos recomendados de SQL en cuanto a las versiones de SQL admitidas para un rol testigo, consulte ["testigo de creación de reflejos de base de datos"](https://go.microsoft.com/fwlink/p/?LinkId=247345) en la biblioteca msdn.
  
Para configurar la creación de reflejo del servidor, es necesario que primero configure los permisos de la base de datos de SQL correctamente. Para obtener más información, consulte ["configurar cuentas de inicio de sesión para el reflejo de bases de datos o grupos de disponibilidad AlwaysOn (SQL Server)"](https://go.microsoft.com/fwlink/p/?LinkId=268454).
  
Con el reflejo de SQL, el modo de recuperación de bases de datos siempre está configurado como **Completa**. Esto significa que es preciso controlar atentamente el tamaño del registro de transacciones y crear copias de seguridad de los registros de transacciones periódicamente para evitar que los servidores back-end se queden sin espacio en disco. La frecuencia con que se necesitan crear copias de seguridad de los registros de transacciones depende de la tasa de crecimiento del registro, que, a su vez, depende de las transacciones de la base de datos producidas por las actividades del usuario en el grupo de servidores front-end. Recomendamos que determine el crecimiento estimado del registro de transacciones para la carga de trabajo de la implementación de Skype Empresarial, de modo que pueda realizar la planeación en consonancia. En los artículos siguientes encontrará información adicional sobre la administración del registro y la copia de seguridad de SQL:
  
> [!IMPORTANT]
> Usar el generador de topología o cmdlets para configurar y quitar la creación de reflejos de SQL solo se admite cuando los servidores principal, reflejado y testigo (si lo desea) pertenecen al mismo dominio. Si desea configurar la creación del reflejo de SQL entre servidores de dominios diferentes, consulte la documentación de SQL Server. 

> [!NOTE]
> La creación de reflejos de SQL está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019. Los grupos de disponibilidad AlwaysOn, las instancias de clúster de conmutación por error (FCI) AlwaysOn, y los métodos de clúster de conmutación por error de SQL son preferidos con Skype empresarial Server 2019.
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a>Tiempo de recuperación de conmutación por error automática de servidor back-end con la creación de reflejo

Para la conmutación por error automática de servidores back-end con la creación de reflejos, el objetivo de ingeniería para el objetivo de tiempo de recuperación (RTO) es de 5 minutos. Debido a la creación de reflejos sincrónica, no prevemos pérdida de datos durante los errores en el servidor back-end, excepto en raras ocasiones, cuando tanto los servidores front-end como los servidores back-end dejan de funcionar simultáneamente mientras se mueven datos entre los servidores. El objetivo de ingeniería para el objetivo de punto de recuperación (RPO) es de 5 minutos.
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a>Experiencia del usuario durante un error de servidor back-end con la creación de reflejo

La experiencia del usuario durante un error depende de la naturaleza del error y de la topología.
  
Si usa la creación de reflejo de bases de datos y tiene un testigo configurado y se produce un error en la entidad principal, la conmutación por error del servidor back-end se produce de forma rápida y automática. Los usuarios activos no tendrían que notar muchas interrupciones en sus sesiones en curso.
  
Si no hay ningún testigo configurado, tomará algún tiempo que el administrador invoque manualmente la conmutación por error. Durante ese tiempo, los usuarios activos probablemente lo notarán. Continuarán con sus sesiones normalmente durante unos 30 minutos. Si el principal aún no se restaura o un administrador no conmuta por error a la copia de seguridad, entonces los usuarios cambian al modo de resistencia, lo que significa que no pueden realizar tareas que requieran un cambio persistente en Lync Server (como agregar un contacto).
  
Si tanto el servidor back-end principal como el de reflejo fallan o si se produce un error en uno de esos servidores y el testigo, el servidor back-end dejará de estar disponible (incluso si se trata del principal que sigue funcionando). En este caso, los usuarios activos se cambian al modo de resistencia después de algún tiempo.
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a>Grupos de disponibilidad AlwaysOn e instancias de clústeres de conmutación por error AlwaysOn

Skype empresarial Server es compatible con los grupos de disponibilidad AlwaysOn solo como activo/pasivo, no activo/activo. 
  
Para usar grupos de disponibilidad AlwaysOn o instancias de clúster de conmutación por error de AlwaysOn, primero use SQL Server para configurar y configurar la solución de alta disponibilidad. Después, puede usar el generador de topología para asociarlo con un grupo de servidores front-end.

Skype empresarial Server es compatible con el siguiente software de base de datos:

- SQL Server 2019 Enterprise Edition

- SQL Server 2019 Standard Edition con limitaciones, consulte la nota siguiente

- SQL Server 2017 Enterprise Edition

- SQL Server 2017 Standard Edition con limitaciones, consulte la nota siguiente

- SQL Server 2016 Enterprise Edition

- SQL Server 2016 Standard Edition con limitaciones, consulte la nota siguiente

- SQL Server 2014 Enterprise Edition
    
- SQL Server 2012 SP2 y CU2 Enterprise Edition

> [!NOTE]
> SQL Server 2019, 2017 y 2016 son las únicas versiones compatibles con Skype empresarial Server 2019.

> [!NOTE]
> Los grupos de disponibilidad AlwaysOn **no** son compatibles con las ediciones de SQL 2016, 2017 y 2019, pero puede usar siempre en las instancias de clúster de conmutación por error. Para obtener más información [, vea las ediciones y las características compatibles de SQL Server 2016](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017) .
  
> [!IMPORTANT]
> Los nombres de instancia de varias instancias del grupo de disponibilidad AlwaysOn deben ser iguales. 
  
Para conocer los pasos para implementar grupos de disponibilidad AlwaysOn, consulte [implementar un grupo de disponibilidad AlwaysOn en un servidor back-end en Skype empresarial Server](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md).
  
## <a name="sql-server-failover-clustering"></a>Clústeres de conmutación por error de SQL Server

Skype empresarial Server es compatible con el clúster de conmutación por error de SQL Server con el siguiente software de base de datos:
  
- SQL Server 2019, Enterprise Edition y Standard Edition

- SQL Server 2017, Enterprise Edition y Standard Edition

- SQL Server 2016, Enterprise Edition y Standard Edition

- SQL Server 2014, Enterprise Edition y Standard Edition
    
- SQL Server 2012 SP2 y CU2, tanto Enterprise Edition como Standard Edition

Para usar el clúster de conmutación por error de SQL, primero debe configurar y configurar el clúster de SQL Server antes de implementar el grupo de servidores front-end. Para ver los procedimientos recomendados y las instrucciones de configuración para el clúster de conmutación por [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx)error en SQL Server 2012, consulte.

> [!NOTE]
> SQL Server 2019, 2017 y SQL Server 2016 son las únicas versiones compatibles con Skype empresarial Server 2019.
    
Para usar el clúster de conmutación por error de SQL, primero debe configurar y configurar el clúster de SQL Server antes de implementar el grupo de servidores front-end. Para obtener los procedimientos recomendados y las instrucciones de configuración para el clúster de conmutación por error en [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx)SQL Server 2014 y 2016, consulte. Para el clúster de conmutación por error en SQL Server [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx)2008, consulte.
  
Al instalar SQL Server, es preciso instalar también SQL Server Management Studio para administrar las ubicaciones de la base de datos y de los archivos de registro. SQL Server Management Studio se instala como un componente opcional al instalar SQL Server.
  
