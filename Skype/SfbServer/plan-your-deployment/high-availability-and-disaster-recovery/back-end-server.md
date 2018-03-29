---
title: Alta disponibilidad del servidor back-end en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: Obtenga información acerca de las opciones de alta disponibilidad de atrás End Server admitidas Skype para Business Server, incluidos los grupos de disponibilidad AlwaysOn, instancias de clúster de conmutación por error de AlwaysOn, reflejo de la base de datos y organización por clústeres de conmutación por error SQL.
ms.openlocfilehash: f0831ffb757d04e954ece8a1874dffad9e6e74d0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="back-end-server-high-availability-in-skype-for-business-server-2015"></a>Alta disponibilidad del servidor back-end en Skype Empresarial Server 2015
 
Obtenga información acerca de las opciones de alta disponibilidad de atrás End Server admitidas Skype para Business Server, incluidos los grupos de disponibilidad AlwaysOn, instancias de clúster de conmutación por error de AlwaysOn, reflejo de la base de datos y organización por clústeres de conmutación por error SQL.
  
Tiene cuatro opciones para mejorar la alta disponibilidad de sus servidores back-end:
  
- Creación de reflejo de la base de datos
    
- Grupos de disponibilidad AlwaysOn
    
- Instancias de clúster de conmutación por error de AlwaysOn (FCI)
    
- Clústeres de conmutación por error de SQL
    
El uso de una u otra solución es opcional, pero recomendamos mantener la continuidad empresarial de la organización. En caso contrario, tener un servidor de base de datos única caiga podría provocar la pérdida de Skype significativo para los datos de Business Server. 
  
Puede establecer la creación de reflejos de base de datos utilizando sólo el generador de topología. Para grupos de disponibilidad AlwaysOn, instancias de clúster de conmutación por error de AlwaysOn o clústeres de conmutación por error SQL, utilice SQL Server para crear la solución de alta disponibilidad, entonces puede utilizar el generador de topología para asociarlo a un grupo de servidores Front-End.
  
Si utiliza alta disponibilidad del servidor de extremo nuevo en un grupo de Front-End que se empareja con otro grupo de Front-End para recuperación ante desastres, debe utilizar la misma solución de alta disponibilidad de Back End de ambos grupos. 
  
## <a name="database-mirroring"></a>Creación de reflejo de la base de datos

Skype para Business Server soporta el espejado con el software de base de datos siguientes:
  
- 2014, Enterprise Edition y Standard Edition de SQL Server
    
- Service Pack 2 de SQL Server 2012 y CU2, Enterprise Edition y Standard Edition
    
- Service Pack 2 de SQL Server 2008 R2, Enterprise Edition y Standard Edition
    
La creación de reflejo de base de datos asincrónica no se admite para alta disponibilidad de servidor nuevo en Skype para Business Server. En lo que resta de este documento, la creación de reflejo de la base de datos implica la creación de reflejo de la base de datos sincrónica, a menos que se indique lo contrario. 
  
Al implementar la creación de reflejo de base de datos en un grupo de servidores Front-End, se reflejan todos Skype para bases de datos de Business Server en el grupo, incluido el almacén de Administración Central, si se encuentra en este grupo, así como la base de datos de aplicación de grupo de respuesta y el parque de llamada base de datos de aplicación, si esas aplicaciones se ejecutan en el grupo. 
  
Con la creación de reflejo de la base de datos, no es necesario usar el almacenamiento compartido para los servidores. Cada servidor guarda su copia de la base de datos en un almacenamiento local. 
  
Puede optar por implementar una creación de reflejo de la base de datos con o sin un testigo. Recomendamos usar un testigo, porque esto permite que la conmutación por error del servidor back-end sea automática. De lo contrario, un administrador tendrá que invocar manualmente la conmutación por error. Tenga en cuenta que, incluso si se implementa un testigo, un administrador puede invocar manualmente la conmutación por error del servidor back-end, si fuera necesario.
  
Si usa un testigo, puede usar un único testigo para varios pares de servidores back-end. No existe una correspondencia estricta uno a uno entre testigos y pares de servidores back-end. Las implementaciones en las que se emplea un único testigo para varios pares de servidores back-end no son tan resistentes como las topologías con un testigo independiente para cada par de servidor back-end. 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a>Instrucciones para planificar la creación de reflejo del servidor back-end

En general, la configuración de creación de reflejo de SQL entre los dos servidores back-end con un testigo requiere lo siguiente:
  
- Versión del servidor principal de SQL Server debe ser compatible con la creación de reflejos de SQL.
    
- El servidor principal, el reflejo y el testigo (si se implementan) necesitan tener la misma versión de SQL Server. 
    
- El servidor principal y el reflejo necesitan tener la misma edición de SQL Server. El testigo puede tener una edición diferente.
    
Para recomendaciones SQL en términos de qué versiones SQL son compatibles para un rol de testigo, vea ["testigo de reflejo de base de datos"](https://go.microsoft.com/fwlink/p/?LinkId=247345) en MSDN Library.
  
Para configurar la creación de reflejo del servidor, es necesario que primero configure los permisos de la base de datos de SQL correctamente. Para obtener más información, consulte ["Configurar las cuentas de inicio de sesión de reflejo de base de datos o grupos de disponibilidad AlwaysOn (SQL Server)"](https://go.microsoft.com/fwlink/p/?LinkId=268454).
  
Con el reflejo de SQL, el modo de recuperación de bases de datos siempre está configurado como **Completa**. Esto significa que es preciso controlar atentamente el tamaño del registro de transacciones y crear copias de seguridad de los registros de transacciones periódicamente para evitar que los servidores back-end se queden sin espacio en disco. La frecuencia con que se necesitan crear copias de seguridad de los registros de transacciones depende de la tasa de crecimiento del registro, que, a su vez, depende de las transacciones de la base de datos producidas por las actividades del usuario en el grupo de servidores front-end. Recomendamos que determine el crecimiento estimado del registro de transacciones para la carga de trabajo de la implementación de Skype Empresarial, de modo que pueda realizar la planeación en consonancia. En los artículos siguientes encontrará información adicional sobre la administración del registro y la copia de seguridad de SQL:
  
> [!IMPORTANT]
> Mediante el generador de topología o cmdlets para configurar y quitar SQL reflejo sólo se admite cuando el principal, réplica y servidores testigo (si lo desea) pertenecen al mismo dominio. Si desea configurar la creación del reflejo de SQL entre servidores de dominios diferentes, consulte la documentación de SQL Server. 
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a>Tiempo de recuperación de conmutación por error automática de servidor back-end con la creación de reflejo

Para la conmutación por error automática de servidores back-end con la creación de reflejos, el objetivo de ingeniería para el objetivo de tiempo de recuperación (RTO) es de 5 minutos. Debido a la creación de reflejos sincrónica, no prevemos pérdida de datos durante los errores en el servidor back-end, excepto en raras ocasiones, cuando tanto los servidores front-end como los servidores back-end dejan de funcionar simultáneamente mientras se mueven datos entre los servidores. El objetivo de ingeniería para el objetivo de punto de recuperación (RPO) es de 5 minutos.
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a>Experiencia del usuario durante un error de servidor back-end con la creación de reflejo

La experiencia del usuario durante un error depende de la naturaleza del error y de la topología.
  
Si usa la creación de reflejo de bases de datos y tiene un testigo configurado y se produce un error en la entidad principal, la conmutación por error del servidor back-end se produce de forma rápida y automática. Los usuarios activos no tendrían que notar muchas interrupciones en sus sesiones en curso.
  
Si no hay ningún testigo configurado, tomará algún tiempo que el administrador invoque manualmente la conmutación por error. Durante ese tiempo, los usuarios activos probablemente lo notarán. Continuarán con sus sesiones normalmente durante unos 30 minutos. Si el primario todavía, no se restaura, o un administrador no haya dejado sobre la copia de seguridad, los usuarios se cambian a modo de resiliencia, lo que significa que no son capaces de realizar tareas que requieren un cambio persistente en Lync Server (como agregar un contacto).
  
Si tanto el servidor back-end principal como el de reflejo fallan o si se produce un error en uno de esos servidores y el testigo, el servidor back-end dejará de estar disponible (incluso si se trata del principal que sigue funcionando). En este caso, los usuarios activos se cambian al modo de resistencia después de algún tiempo.
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a>Grupos de disponibilidad AlwaysOn e instancias de clústeres de conmutación por error AlwaysOn

Grupos de disponibilidad AlwaysOn y AlwaysOn instancias de clúster de conmutación por error sólo son compatibles con SQL Server 2014 Enterprise Edition y Enterprise Edition de SQL Server 2012. Skype para Business Server admite grupos de disponibilidad AlwaysOn sólo como activo/pasivo, no activo/activo. 
  
Para utilizar grupos de disponibilidad AlwaysOn o instancias de clúster de conmutación por error de AlwaysOn, primero utilizar SQL Server para instalar y configurar la solución de alta disponibilidad. A continuación, puede utilizar el generador de topología para asociarlo a un grupo de servidores Front-End.
  
> [!IMPORTANT]
> Nombres de instancia para varias instancias del grupo de disponibilidad AlwaysOn deben ser el mismo. 
  
Para conocer los pasos para implementar grupos de disponibilidad AlwaysOn, vea [implementar un grupo de disponibilidad AlwaysOn en un servidor de fondo detrás de Skype para Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md).
  
## <a name="sql-server-failover-clustering"></a>Clústeres de conmutación por error de SQL Server

Skype para Business Server admite clústeres con el siguiente software de base de datos de conmutación por error de SQL Server:
  
- 2014, Enterprise Edition y Standard Edition de SQL Server
    
- Service Pack 2 de SQL Server 2012 y CU2, Enterprise Edition y Standard Edition
    
- Service Pack 2 de SQL Server 2008 R2, Enterprise Edition y Standard Edition
    
Para utilizar el clúster de conmutación por error SQL, primero debe configurar y configurar el clúster de SQL Server antes de implementar el grupo de servidores Front-End. Para recomendaciones e instrucciones de instalación para conmutación por error de SQL Server 2012, consulte [https://technet.microsoft.com/en-us/library/hh231721.aspx](https://technet.microsoft.com/en-us/library/hh231721.aspx). Para la conmutación por error de SQL Server 2008, consulte [https://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/en-us/library/ms189134%28v=sql.105%29.aspx).
  
Al instalar SQL Server, es preciso instalar también SQL Server Management Studio para administrar las ubicaciones de la base de datos y de los archivos de registro. SQL Server Management Studio se instala como un componente opcional al instalar SQL Server.
  

