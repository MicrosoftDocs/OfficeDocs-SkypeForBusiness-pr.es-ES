---
title: Recuperación ante desastres del grupo front-end en Skype Empresarial Server
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
ms.assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
description: Para la recuperación ante desastres, Skype Empresarial Server el emparejamiento de grupos con conmutación por error en caso de que un grupo de servidores se desalome.
ms.openlocfilehash: a7e658e10718ac45ee6c2122433137ac4a198a459baa0171aec2453963636d32
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276635"
---
# <a name="front-end-pool-disaster-recovery-in-skype-for-business-server"></a>Recuperación ante desastres del grupo front-end en Skype Empresarial Server
 
Para la recuperación ante desastres, Skype Empresarial Server el emparejamiento de grupos con conmutación por error en caso de que un grupo de servidores se desalome.
  
Para las opciones de recuperación ante desastres más sólidas de Skype Empresarial Server, implemente pares de grupos de servidores front-end en dos sitios geográficamente dispersos. Cada sitio tiene un grupo de servidores front-end que está emparejado con un grupo de servidores front-end correspondiente en el otro sitio. Ambos sitios están activos y el servicio de copia de seguridad proporciona replicación de datos en tiempo real para mantener sincronizados los grupos de servidores. Consulte [Deploy paired Front End pools for disaster recovery in Skype Empresarial Server](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md) if you want to implement Front End pool pairing.
  
![Muestra grupos de servidores front-end en dos sitios diferentes, emparejados entre sí](../../media/f74533c0-a10e-4f18-85a8-b9a008497573.jpg)
  
Si se produce un error en el grupo de servidores de un sitio, puede conmutar por error los usuarios de ese grupo al grupo del otro sitio, que sirve a todos los usuarios de ambos grupos. Para la planeación de capacidad, debe diseñar cada grupo para poder controlar la carga de trabajo de todos los usuarios de ambos grupos en caso de desastre.
  
Dos centros de datos que incluyen grupos de servidores front-end emparejados entre sí pueden estar separados por cualquier distancia. Se recomienda emparejar dos centros de datos en la misma región del mundo, con vínculos de alta velocidad entre ellos. 
  
Es posible tener dos centros de datos en todas las regiones del mundo, pero podría provocar una pérdida de datos mayor si hay un desastre, debido a la latencia en la replicación de datos.
  
Al planear los grupos de servidores que se van a emparejar, debe tener en cuenta que solo se admiten los emparejamientos siguientes:
  
- Los grupos de servidores de Enterprise Edition se pueden emparejar solo con otros grupos de servidores de Enterprise Edition. De manera similar, los grupos de servidores de Standard Edition solo se pueden emparejar con otros grupos de servidores de Standard Edition.
    
- Los grupos de servidores físicos se pueden emparejar solo con otros grupos de servidores físicos. De manera similar, los grupos de servidores virtuales solo se pueden emparejar con otros grupos de servidores virtuales.
    
- Los grupos de servidores emparejados deben ejecutar el mismo sistema operativo base.
    
Ningún Generador de topologías ni ninguna validación de topología prohibirá el emparejamiento de dos grupos de servidores de forma que no siga estas recomendaciones. Por ejemplo, el Generador de topologías permite emparejar un grupo de servidores de Enterprise Edition con un grupo de servidores de Standard Edition. Sin embargo, no se admiten estos tipos de emparejamientos.
  
## <a name="backup-registrar-relationships-and-survivable-branch-appliances"></a>Relaciones de registrador de copia de seguridad y aplicaciones de sucursal con funciones de supervivencia

Además de proporcionar la capacidad de recuperación ante desastres, dos grupos de servidores emparejados sirven como registradores de copia de seguridad entre sí. Cada grupo puede ser la copia de seguridad de otro grupo de servidores front-end.
  
Aunque las relaciones de copia de seguridad entre dos grupos de servidores front-end deben ser 1:1 y simétricas, cada grupo de servidores front-end también puede ser el registrador de copias de seguridad para cualquier número de aplicaciones de sucursal con funciones de supervivencia.
  
Tenga en cuenta que Skype Empresarial no amplía la compatibilidad con la recuperación ante desastres a los usuarios que se alomen en una aplicación de sucursal con funciones de supervivencia. Si un grupo de servidores front-end que sirve como copia de seguridad para una aplicación de sucursal con funciones de supervivencia se desvía, los usuarios que han iniciado sesión en la aplicación de sucursal con funciones de supervivencia entran en modo de resistencia, aunque los usuarios que se encuentran en el grupo front-end tienen una con errores en el grupo de servidores front-end de copia de seguridad.
  
## <a name="recovery-time-for-pool-failover-and-pool-failback"></a>Tiempo de recuperación para la conmutación por error del grupo y la conmutación por recuperación del grupo

Para la conmutación por error del grupo y la conmutación por recuperación del grupo, el objetivo de ingeniería del objetivo de tiempo de recuperación (RTO) es de 15 a 20 minutos. Este es el tiempo necesario para que se produzca la conmutación por error, después de que los administradores determinen que hubo un desastre e iniciaron los procedimientos de conmutación por error. No incluye el tiempo necesario para que el administrador evalúe la situación y tome una decisión, como tampoco el tiempo necesario para que los usuarios vuelvan a iniciar sesión una vez que finalice la conmutación por error.
  
Para la conmutación por error del grupo y la conmutación por recuperación del grupo, el objetivo de ingeniería para el objetivo de punto de recuperación (RPO) es 5 minutos. Esto representa la medición de tiempo de los datos que se podría perder debido a un desastre, debido a la latencia de replicación del Servicio de copia de seguridad. Por ejemplo, si un grupo baja a las 10:00 a.m. y rpo es 5 minutos, los datos escritos en el grupo entre las 9:55 a.m. y a las 10:00 a.m., es posible que no se haya replicado en el grupo de copia de seguridad y se perdería.
  
En todos los números de RTO y RPO de este documento se asume que los dos centros de datos se encuentran en la misma región del mundo con un transporte de alta velocidad y baja latencia entre las dos ubicaciones. Estos números se miden para un grupo de servidores con 40.000 usuarios activos simultáneamente y 200.000 usuarios habilitados para Skype Empresarial con respecto a un modelo de usuario predefinido en el que no hay ningún retraso en la replicación de datos. Están sujetos a cambios a partir de las pruebas de rendimiento y validación.
  
## <a name="central-management-store-failover"></a>Conmutación por error del almacén de administración central

El almacén de administración central contiene datos de configuración sobre los servidores y servicios de la implementación. Cada Skype Empresarial Server implementación incluye un almacén de administración central, que está hospedado por el servidor back-end de un grupo de servidores front-end.
  
Si empareja el grupo que hospeda el almacén de administración central, se configura una base de datos del almacén de administración central de copia de seguridad en el grupo de copias de seguridad. En cualquier momento, una de las dos bases de datos del almacén de administración central está activa y la otra es una espera. El servicio de copia de seguridad replica el contenido desde la base de datos activa hasta la espera.
  
![Muestra dos grupos de servidores front-end, uno con el almacén de CMS activo y otro con el almacén de CMS de copia de seguridad pasiva](../../media/aa479398-eb56-4854-8d50-1eff39c58a56.jpg)
  
Durante una conmutación por error del grupo que implica el grupo de servidores que hospeda el almacén de administración central, debe conmutar por error el almacén de administración central antes de conmutar por error el grupo de servidores front-end.
  
Después de reparar el desastre, no es necesario devolver la conmutación por recuperación del almacén de administración central. El almacén de administración central puede permanecer en el grupo al que se le ha fallado.
  
Los objetivos de ingeniería para la conmutación por error del almacén de administración central son 5 minutos para el objetivo de tiempo de recuperación (RTO) y 5 minutos para el objetivo de punto de recuperación (RPO).
  
## <a name="front-end-pool-pairing-data-security"></a>Seguridad de datos de emparejamiento de grupo front-end

El servicio de copia de seguridad transfiere datos de usuario y contenido de conferencia entre dos grupos de servidores front-end emparejados continuamente. Los datos de usuario contienen URI de SIP de usuario, así como programaciones de conferencia, listas de contactos y configuración. El contenido de la conferencia incluye PowerPoint de Microsoft, así como pizarras usadas en conferencias.
  
Desde el grupo de origen, estos datos se exportan desde el almacenamiento local, se comprimen y, a continuación, se transfieren al grupo de servidores de destino, donde se descomprimen e importan al almacenamiento local. El Servicio de copia de seguridad supone que el vínculo de comunicaciones entre los dos centros de datos está dentro de la red corporativa protegida de Internet. No cifra los datos transferidos entre los dos centros de datos ni los datos se encapsulan de forma nativa dentro de un protocolo seguro, como HTTPS. Por lo tanto, es posible un ataque man-in-the-middle del personal interno dentro de la red corporativa.
  
Cualquier empresa que implemente Skype Empresarial Server varios centros de datos y use la característica de recuperación ante desastres debe asegurarse de que el tráfico entre centros de datos está protegido por su intranet corporativa. Las empresas que se preocupan por la protección contra ataques internos deben proteger los vínculos de comunicación entre los centros de datos. Este es un requisito estándar que también ayuda a protec muchos otros tipos de datos confidenciales corporativos transferidos entre centros de datos.
  
Si bien el riesgo de ataques de tipo "man in the middle" dentro de la red corporativa es real, es relativamente limitado en comparación con la exposición del tráfico a Internet. En concreto, los datos de usuario expuestos por el servicio de copia de seguridad (como uri de SIP) suelen estar disponibles para todos los empleados de la empresa a través de otros medios, como la Libreta global de direcciones u otro software de directorio. Por lo tanto, el foco debe centrarse en proteger la WAN entre los dos centros de datos cuando se usa el servicio de copia de seguridad para copiar datos entre los dos grupos emparejados.
  
### <a name="mitigating-security-risks"></a>Mitigación de riesgos de seguridad

Tiene muchas formas de mejorar la protección de seguridad para el tráfico del servicio de copia de seguridad. Esto va desde restringir el acceso a los centros de datos hasta proteger el transporte WAN entre los dos centros de datos. En la mayoría de los casos, las Skype Empresarial Server que ya tienen la infraestructura de seguridad necesaria en su lugar. Para las empresas que buscan orientación, Microsoft proporciona una solución como ejemplo de cómo crear una infraestructura de TI segura. Para obtener más información, vea [https://go.microsoft.com/fwlink/p/?LinkId=268544](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725770(v=ws.10)) . 
  
No implicamos que sea la única solución, ni implicamos que sea la solución preferida para Skype Empresarial Server. Se recomienda que los clientes empresariales elijan la solución según sus necesidades específicas, en función de su infraestructura y requisitos de seguridad de TI. La solución de Microsoft de ejemplo emplea IPSec y la directiva de grupo para el aislamiento de servidores y dominios.
  
Otra solución posible es usar IPSec solo para ayudar a proteger los datos enviados por el propio servicio de copia de seguridad. Si elige este método, debe configurar las reglas de IPSec para el protocolo SMB para los siguientes servidores, donde el grupo A y el grupo B son dos grupos de servidores front-end emparejados.
  
- El servicio SMB (TCP/445) de cada servidor front-end del grupo A al almacén de archivos usado por el grupo B.
    
- El servicio SMB (TCP/445) de cada servidor front-end del grupo B al almacén de archivos usado por el grupo A.
    
> [!CAUTION]
>  IPsec no está pensado como un reemplazo para la seguridad de nivel de aplicación, como SSL/TLS. Una ventaja de usar IPsec es que puede proporcionar seguridad de tráfico de red para las aplicaciones existentes sin tener que cambiarlas. Las empresas que quieran proteger el transporte entre los dos centros de datos deben consultar a sus respectivos proveedores de hardware de red sobre formas de configurar conexiones WAN seguras mediante el equipamiento del proveedor.
  
## <a name="see-also"></a>Consulte también

[Implementar grupos de servidores front-end emparejados para la recuperación ante desastres en Skype Empresarial Server](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md)