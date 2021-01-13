---
title: Recuperación ante desastres del grupo de servidores front-end en Skype Empresarial Server
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
description: Para la recuperación ante desastres, Skype Empresarial Server ofrece el emparejamiento de grupos de servidores con conmutación por error en caso de que un grupo de servidores se desalome.
ms.openlocfilehash: d77a0d56c7a3e3d80c6e735fd6eff178606f667a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802920"
---
# <a name="front-end-pool-disaster-recovery-in-skype-for-business-server"></a>Recuperación ante desastres del grupo de servidores front-end en Skype Empresarial Server
 
Para la recuperación ante desastres, Skype Empresarial Server ofrece el emparejamiento de grupos de servidores con conmutación por error en caso de que un grupo de servidores se desalome.
  
Para las opciones de recuperación ante desastres más sólidas de Skype Empresarial Server, implemente pares de grupos de servidores front-end en dos sitios geográficamente dispersos. Cada sitio tiene un grupo de servidores front-end que está emparejado con un grupo de servidores front-end correspondiente en el otro sitio. Ambos sitios están activos y el servicio de copia de seguridad proporciona replicación de datos en tiempo real para mantener los grupos sincronizados. Consulte [Implementar grupos de servidores front-end](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md) emparejados para la recuperación ante desastres en Skype Empresarial Server si desea implementar el emparejamiento de grupos de servidores front-end.
  
![Muestra grupos de servidores front-end en dos sitios diferentes, emparejados entre sí](../../media/f74533c0-a10e-4f18-85a8-b9a008497573.jpg)
  
Si se produce un error en el grupo de servidores de un sitio, puede conmutar por error los usuarios de ese grupo al grupo de servidores del otro sitio, que a continuación da servicio a todos los usuarios de ambos grupos. Para la planeación de la capacidad, debe diseñar cada grupo para poder controlar la carga de trabajo de todos los usuarios de ambos grupos en caso de desastre.
  
Dos centros de datos que incluyen grupos de servidores front-end emparejados entre sí pueden estar separados por cualquier distancia. Se recomienda emparejar dos centros de datos en la misma región del mundo, con vínculos de alta velocidad entre ellos. 
  
Tener dos centros de datos en regiones del mundo es posible, pero podría provocar una pérdida de datos mayor si se produce un desastre, debido a la latencia en la replicación de datos.
  
Al planear qué grupos de servidores emparejar, debe tener en cuenta que solo se admiten los siguientes emparejamientos:
  
- Los grupos de servidores de Enterprise Edition se pueden emparejar solo con otros grupos de servidores de Enterprise Edition. De manera similar, los grupos de servidores de Standard Edition solo se pueden emparejar con otros grupos de servidores de Standard Edition.
    
- Los grupos de servidores físicos se pueden emparejar solo con otros grupos de servidores físicos. De manera similar, los grupos de servidores virtuales solo se pueden emparejar con otros grupos de servidores virtuales.
    
- Los grupos de servidores emparejados deben ejecutar el mismo sistema operativo base.
    
Ningún Generador de topologías ni ninguna validación de topología prohibirá el emparejamiento de dos grupos de servidores de forma que no siga estas recomendaciones. Por ejemplo, el Generador de topologías permite emparejar un grupo de servidores de Enterprise Edition con un grupo de servidores de Standard Edition. Sin embargo, no se admiten estos tipos de emparejamientos.
  
## <a name="backup-registrar-relationships-and-survivable-branch-appliances"></a>Relaciones de registrador de copia de seguridad y aplicaciones de sucursal con funciones de supervivencia

Además de proporcionar la capacidad de recuperación ante desastres, dos grupos de servidores emparejados sirven como registradores de copia de seguridad entre sí. Cada grupo de servidores puede ser la copia de seguridad de un solo grupo de servidores front-end.
  
Aunque las relaciones de copia de seguridad entre dos grupos de servidores front-end deben ser 1:1 y simétricas, cada grupo de servidores front-end también puede ser el registrador de copia de seguridad para cualquier número de aplicaciones de sucursal con funciones de supervivencia.
  
Tenga en cuenta que Skype Empresarial no amplía la compatibilidad con la recuperación ante desastres a los usuarios que están en una aplicación de sucursal con funciones de supervivencia. Si un grupo de servidores front-end que sirve como copia de seguridad de una aplicación de sucursal con funciones de supervivencia se desvía, los usuarios que han iniciado sesión en la aplicación de sucursal con funciones de supervivencia entran en modo de resistencia aunque los usuarios que se encuentran en el grupo de servidores front-end se con errores en el grupo de servidores front-end de reserva.
  
## <a name="recovery-time-for-pool-failover-and-pool-failback"></a>Tiempo de recuperación para la conmutación por error y la conmutación por recuperación del grupo de servidores

Para la conmutación por error del grupo y la conmutación por recuperación del grupo de servidores, el objetivo de ingeniería para el objetivo de tiempo de recuperación (RTO) es de 15 a 20 minutos. Este es el tiempo necesario para que se produzca la conmutación por error, después de que los administradores determinaron que hubo un desastre e iniciaron los procedimientos de conmutación por error. No incluye el tiempo necesario para que el administrador evalúe la situación y tome una decisión, como tampoco el tiempo necesario para que los usuarios vuelvan a iniciar sesión una vez que finalice la conmutación por error.
  
Para la conmutación por error del grupo y la conmutación por recuperación del grupo de servidores, el objetivo de ingeniería para el objetivo de punto de recuperación (RPO) es de 5 minutos. Esto representa la medición de tiempo de los datos que se podría perder debido a un desastre, debido a la latencia de replicación del Servicio de copia de seguridad. Por ejemplo, si un grupo de servidores cae a las 10:00 a.m. y el RPO es de 5 minutos, los datos se escriben en el grupo entre las 9:55 a.m. y las 10:00 a.m. puede que no se haya replicado en el grupo de copia de seguridad y se perdería.
  
En todos los números de RTO y RPO de este documento se asume que los dos centros de datos se encuentran en la misma región del mundo con un transporte de alta velocidad y baja latencia entre las dos ubicaciones. Estos números se miden para un grupo de servidores con 40.000 usuarios activos simultáneamente y 200.000 usuarios habilitados para Skype Empresarial con respecto a un modelo de usuario predefinido en el que no hay ningún trabajo pendiente en la replicación de datos. Están sujetos a cambios a partir de las pruebas de rendimiento y validación.
  
## <a name="central-management-store-failover"></a>Conmutación por error del almacén de administración central

El almacén de administración central contiene datos de configuración sobre los servidores y servicios de la implementación. Cada implementación de Skype Empresarial Server incluye un almacén de administración central, que se hospeda en el servidor back-end de un grupo de servidores front-end.
  
Si empareja el grupo de servidores que hospeda el almacén de administración central, se configura una base de datos del almacén de administración central de copia de seguridad en el grupo de servidores de copia de seguridad. En cualquier momento, una de las dos bases de datos del almacén de administración central está activa y la otra está en espera. El servicio de copia de seguridad replica el contenido de la base de datos activa en modo de espera.
  
![Muestra dos grupos de servidores front-end, uno con el almacén de CMS activo y el otro con el almacén DE CMS de copia de seguridad pasiva](../../media/aa479398-eb56-4854-8d50-1eff39c58a56.jpg)
  
Durante una conmutación por error de grupo que implica el grupo de servidores que hospeda el almacén de administración central, debe conmutar por error el almacén de administración central antes de conmutar por error el grupo de servidores front-end.
  
Después de reparar el desastre, no es necesario conmutar por recuperación el almacén de administración central. El almacén de administración central puede permanecer en el grupo en el que se le ha fallado.
  
Los objetivos de ingeniería para la conmutación por error del almacén de administración central son 5 minutos para el objetivo de tiempo de recuperación (RTO) y 5 minutos para el objetivo de punto de recuperación (RPO).
  
## <a name="front-end-pool-pairing-data-security"></a>Seguridad de datos de emparejamiento de grupos de servidores front-end

El servicio de copia de seguridad transfiere continuamente datos de usuario y contenido de conferencia entre dos grupos de servidores front-end emparejados. Los datos de usuario contienen URI de SIP de usuario, así como programaciones de conferencias, listas de contactos y configuración. El contenido de conferencia incluye cargas de Microsoft PowerPoint, así como pizarras usadas en conferencias.
  
Desde el grupo de origen, estos datos se exportan desde el almacenamiento local, se comprimen y, a continuación, se transfieren al grupo de servidores de destino, donde se descomprimen e importan al almacenamiento local. El Servicio de copia de seguridad supone que el vínculo de comunicaciones entre los dos centros de datos está dentro de la red corporativa protegida de Internet. No cifra los datos transferidos entre los dos centros de datos, ni los datos se encapsulan de forma nativa dentro de un protocolo seguro, como HTTPS. Por lo tanto, es posible un ataque de tipo "man in the middle" por parte del personal interno de la red corporativa.
  
Cualquier empresa que implemente Skype Empresarial Server en varios centros de datos y use la característica de recuperación ante desastres debe asegurarse de que el tráfico entre centros de datos está protegido por su intranet corporativa. Las empresas que se preocupan por la protección contra ataques internos deben proteger los vínculos de comunicación entre los centros de datos. Este es un requisito estándar que también ayuda a proteger muchos otros tipos de datos confidenciales corporativos transferidos entre centros de datos.
  
Si bien el riesgo de ataques de tipo "man in the middle" dentro de la red corporativa es real, es relativamente limitado en comparación con la exposición del tráfico a Internet. En concreto, los datos de usuario expuestos por el servicio de copia de seguridad (como URI de SIP) están generalmente disponibles para todos los empleados de la empresa a través de otros medios, como la Libreta global de direcciones u otro software de directorio. Por lo tanto, debe centrarse en proteger la WAN entre los dos centros de datos cuando se usa el servicio de copia de seguridad para copiar datos entre los dos grupos emparejados.
  
### <a name="mitigating-security-risks"></a>Mitigación de riesgos de seguridad

Tiene muchas formas de mejorar la protección de seguridad para el tráfico del servicio de copia de seguridad. Esto va desde restringir el acceso a los centros de datos hasta proteger el transporte WAN entre los dos centros de datos. En la mayoría de los casos, es posible que las empresas que implementan Skype Empresarial Server ya tengan la infraestructura de seguridad necesaria. Para las empresas que buscan orientación, Microsoft proporciona una solución como ejemplo de cómo crear una infraestructura de TI segura. Para obtener más información, vea [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?LinkId=268544) . 
  
No implicamos que sea la única solución ni que sea la solución preferida para Skype Empresarial Server. Recomendamos que los clientes empresariales elijan la solución que mejor se adapte a sus necesidades específicas, en función de sus requisitos y su infraestructura de seguridad de TI. La solución de Microsoft de ejemplo emplea IPSec y la directiva de grupo para el aislamiento de servidores y dominios.
  
Otra solución posible es usar IPSec solo para ayudar a proteger los datos enviados por el propio servicio de copia de seguridad. Si elige este método, debe configurar las reglas IPSec para el protocolo SMB para los siguientes servidores, donde los grupos A y B son dos grupos de servidores front-end emparejados.
  
- El servicio SMB (TCP/445) de cada servidor front-end del grupo A al almacén de archivos usado por el grupo B.
    
- El servicio SMB (TCP/445) de cada servidor front-end del grupo B al almacén de archivos usado por el grupo A.
    
> [!CAUTION]
>  IPsec no está pensado como sustituto de la seguridad de nivel de aplicación, como SSL/TLS. Una ventaja de usar IPsec es que puede proporcionar seguridad de tráfico de red para las aplicaciones existentes sin tener que cambiarlas. Las empresas que solo desean proteger el transporte entre los dos centros de datos deben consultar a sus respectivos proveedores de hardware de red sobre las formas de configurar conexiones WAN seguras mediante el equipo del proveedor.
  
## <a name="see-also"></a>Vea también

[Implementar grupos de servidores front-end emparejados para la recuperación ante desastres en Skype Empresarial Server](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md)
