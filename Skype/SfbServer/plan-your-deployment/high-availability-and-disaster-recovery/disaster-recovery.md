---
title: Recuperación ante desastres del grupo de servidores front-end en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
description: Para la recuperación ante desastres, Skype para Business Server ofrece el emparejamiento con conmutación por error en caso de funcionar un grupo de servidores del grupo de servidores.
ms.openlocfilehash: 77d0f681b8fc4b88837ed46d1afc6bb415f46932
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19505037"
---
# <a name="front-end-pool-disaster-recovery-in-skype-for-business-server-2015"></a>Recuperación ante desastres del grupo de servidores front-end en Skype Empresarial Server 2015
 
Para la recuperación ante desastres, Skype para Business Server ofrece el emparejamiento con conmutación por error en caso de funcionar un grupo de servidores del grupo de servidores.
  
Para el más sólidas opciones recuperación ante desastres en Skype para Business Server, implemente pares de grupos de servidores Front-End entre dos sitios geográficamente dispersos. Cada sitio tiene un grupo de servidores front-end que se empareja con un grupo de servidores front-end correspondiente en otro sitio. Ambos sitios se encuentran activos, y el servicio de copia de seguridad proporciona la replicación de datos en tiempo real a fin de mantener los grupos sincronizados. Si desea implementar el emparejamiento de grupo de servidores Front-End, consulte [Deploy emparejada grupos de Front-End para la recuperación ante desastres en Skype para Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md) .
  
![Muestra grupos de servidores front-end en dos sitios distintos, emparejados entre sí](../../media/f74533c0-a10e-4f18-85a8-b9a008497573.jpg)
  
Si el grupo de un sitio falla, puedes realizar la conmutación por error de los usuarios de dicho grupo al grupo del otro sitio, que proporcionará servicios a todos usuarios de ambos grupos. Para la planificación de la capacidad, necesitas diseñar cada grupo para que pueda gestionar la carga de trabajo de todos los usuarios de ambos grupos en caso de que ocurra un desastre.
  
Dos centros de datos que incluyan grupos de servidores front-end emparejados entre sí pueden encontrarse a cualquier distancia. Recomendamos que emparejes dos centros de datos en la misma región del mundo y con vínculos de alta velocidad entre sí. 
  
Tener dos centros de datos en regiones del mundo, es posible, pero podría provocar la pérdida de datos mayor si no hay un desastre, debido a la latencia de replicación de datos.
  
Al planear que grupos de servidores a par, debe tener en cuenta que se admiten sólo los emparejamientos siguientes:
  
- Los grupos de servidores de Enterprise Edition se pueden emparejar solo con otros grupos de servidores de Enterprise Edition. De manera similar, los grupos de servidores de Standard Edition solo se pueden emparejar con otros grupos de servidores de Standard Edition.
    
- Los grupos de servidores físicos se pueden emparejar solo con otros grupos de servidores físicos. De manera similar, los grupos de servidores virtuales solo se pueden emparejar con otros grupos de servidores virtuales.
    
- Los grupos que estén emparejados juntos necesitan ejecutarse en el mismo sistema operativo base.
    
Ni el generador de topologías ni la validación de topología prohibirán el emparejamiento de dos grupos de servidores de un modo que no siga estas recomendaciones. Por ejemplo, el generador de topologías permite emparejar un grupo de servidores Enterprise Edition con un grupo de servidores Standard Edition. En realidad, estos tipos de emparejamientos no se admiten.
  
## <a name="backup-registrar-relationships-and-survivable-branch-appliances"></a>Copia de seguridad de relaciones entre registradores y aplicaciones de sucursal con funciones de supervivencia

Además de proporcionar la capacidad de recuperación ante desastres, dos grupos de servidores emparejados sirven como registradores de copia de seguridad entre sí. Cada grupo de servidores puede ser la copia de seguridad para un solo otros servidores Front-End.
  
Aunque las relaciones de copia de seguridad entre dos grupos de servidores Front-End deben ser 1:1 y simétricas, cada grupo de servidores Front-End aún también puede ser el registrador de copia de seguridad de cualquier número de aplicaciones de sucursal con funciones de supervivencia.
  
Ten en cuenta que Skype Empresarial no amplía el soporte de la recuperación ante desastres a usuarios alojados en una aplicación de sucursal con funciones de supervivencia. Si un grupo de servidores front-end que sirve como copia de seguridad de una aplicación de sucursal con funciones de supervivencia deja de estar disponible, los usuarios que hayan iniciado sesión en dicha aplicación de sucursal con funciones de supervivencia entrarán al modo de resistencia, incluso después de que los usuarios alojados en el grupo de servidores front-end hayan conmutado por error al grupo de servidores front-end de copia de seguridad.
  
## <a name="recovery-time-for-pool-failover-and-pool-failback"></a>Tiempo de recuperación para la conmutación por error y por recuperación del grupo de servidores

Para la conmutación por error y por recuperación del grupo de servidores, el objetivo de ingeniería para el objetivo de tiempo de recuperación (RTO) es de 15 a 20 minutos. Este es el tiempo necesario para que tenga lugar la conmutación por error, una vez que los administradores hayan determinado que se ha producido un desastre e inicien los procedimientos de conmutación por error. No incluye el tiempo necesario para que los administradores evalúen la situación y tomen una decisión, como tampoco el tiempo necesario para que los usuarios vuelvan a iniciar sesión una vez que finalice la conmutación por error.
  
Para el grupo de servidores de conmutación por error y conmutación por recuperación del grupo de servidores, el destino de ingeniería para objetivo de punto de recuperación (RPO) es de 5 minutos. Esto representa la medida de tiempo de datos que se podrían perder debido a del desastre, debido a la latencia de replicación del servicio de copia de seguridad. Por ejemplo, si un grupo de servidores deja de funcionar a las 10:00 A.M., y el RPO es de 5 minutos, los datos escritos en el grupo de servidores entre 9:55 A.M. y .might 10:00 A.M. no se ha replicado en el grupo de copia de seguridad y se perderán.
  
Para todas las cantidades de RTO y RPO de este documento se asume que los dos centros de datos se encuentran en la misma región del mundo con un transporte de alta velocidad y baja latencia entre los dos sitios. Estas cantidades se miden para un grupo de 40 000 usuarios activos simultáneamente y 200 000 usuarios habilitados para Lync con respecto a un modelo de usuario predefinido en el que no hay trabajo pendiente en la replicación de datos. Están sujetas a cambios a partir de las pruebas de rendimiento y validación.
  
## <a name="central-management-store-failover"></a>Conmutación por error del almacén de administración central

El almacén de administración central contiene datos de configuración sobre los servidores y los servicios de tu implementación. Cada Skype para la implementación de Business Server incluye un almacén de Administración Central, que está hospedado en el servidor Back-End de un grupo de servidores Front-End.
  
Si emparejas el grupo que hospeda al almacén de administración central, se configura una base de datos del almacén de administración central en el grupo de copia de seguridad. En todo momento, una de las dos bases de datos del almacén de administración central está activa y la otra en modo de espera. El servicio de copia de seguridad replica el contenido desde la base de datos activa a la que se encuentra en modo de espera.
  
![Muestra dos grupos de servidores front-end, uno con el almacén de CMS activo y el otro con el almacén de CMS de copia de seguridad pasiva](../../media/aa479398-eb56-4854-8d50-1eff39c58a56.jpg)
  
Durante una conmutación por error que implica el grupo de servidores que hospeda el almacén de Administración Central, deberá conmutar el almacén de Administración Central antes de que producirá un error en el grupo de servidores Front-End.
  
Después de que se repara el desastre, no es necesario llevar a cabo la conmutación por recuperación del almacén de administración central. El almacén de administración central puede permanecer en el grupo en el que se lo colocó en la conmutación por error.
  
Los objetivos de ingeniería para conmutación por error de almacén de Administración Central son 5 minutos para el objetivo de tiempo de recuperación (RTO) y 5 minutos para la recuperación de punto de recuperación (RPO).
  
## <a name="front-end-pool-pairing-data-security"></a>Seguridad de datos en el emparejamiento de grupos de servidores front-end

De forma continua, los servicios de copia de seguridad transfieren datos de usuario y contenido de conferencias entre dos grupos de servidores front-end emparejados. Los datos de usuario incluyen URI de SIP, así como también programas de conferencias, configuraciones y listas de contactos. El contenido de conferencias incluye cargas de Microsoft PowerPoint, además de pizarras utilizadas en conferencias.
  
Desde el grupo de origen, estos datos se exportan desde el almacenamiento local, en archivos comprimidos y, luego, se transfieren al grupo de destino, donde se descomprimen e importan al almacenamiento local. El servicio de copia de seguridad supone que el vínculo de comunicación entre los dos centros de datos se encuentra dentro de la red corporativa y que se protege de Internet. No cifra los datos transferidos entre los dos centros de datos, ni encapsula los datos de forma nativa en un protocolo de seguridad (como HTTPS). Por lo tanto, es posible un ataque de man-in-the-middle desde personal interno dentro de la red corporativa.
  
Cualquier empresa que implementa Skype para Business Server en varios centros de datos y usa la característica de recuperación ante desastres debe asegurarse de que el tráfico entre los centros de datos está protegido por su Intranet corporativa. Las empresas que tienen en cuenta la protección frente a ataques internos necesitan proteger los vínculos de comunicación entre los centros de datos. Este es un requisito estándar que también ayuda a proteger muchos más tipos de datos confidenciales corporativos que se transfieren entre los centros de datos.
  
Si bien el riesgo de ataques de tipo "Man in the middle" dentro de la red corporativa es real, es relativamente limitado en comparación con la exposición del tráfico en Internet. Concretamente, los datos de usuario que expone el servicio de copia de seguridad (como los URI de SIP) suelen estar disponibles para todos los empleados de la compañía a través de otros medios, como la libreta de direcciones global de Exchange u otro software de directorio. Por ello, necesitas centrarte en proteger la WAN entre los dos centros de datos cuando se usa el servicio de copia de seguridad para copiar datos entre los dos grupos de servidores emparejados.
  
### <a name="mitigating-security-risks"></a>Reducir los riesgos de seguridad

Posiblemente cuentes con varias maneras de mejorar la protección de seguridad para el tráfico del servicio de copia de seguridad. Estas maneras varían desde restringir el acceso a los centros de datos hasta proteger el transporte de WAN entre los dos centros de datos. En la mayoría de los casos, las empresas la implementación de Skype para Business Server que ya tenga la infraestructura de seguridad necesarios en su lugar. Para aquellas empresas que necesitan una guía, Microsoft brinda una solución como un ejemplo de cómo desarrollar una infraestructura de TI segura. Para obtener información detallada, consulte [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?LinkId=268544). 
  
No se implica que es la única solución ni se implica que es la solución preferida para Skype para Business Server. Recomendamos que los clientes empresariales elijan la solución que se ajuste a sus necesidades específicas, de acuerdo con los requisitos y la infraestructura de TI que posean. El ejemplo de Microsoft emplea IPSec y directivas de grupo para el servidor y el aislamiento de dominios.
  
Otra posible solución consiste en usar IPsec solamente para que proteger los datos enviados por el propio servicio de copia de seguridad sea más fácil. Si eliges este método, necesitarás configurar las reglas IPsec del protocolo SMB para los siguientes servidores, donde los grupos A y B son dos grupos de servidores front-end emparejados.
  
- El servicio de SMB (TCP/445) de cada servidor Front-End del grupo de servidores A para el almacén de archivos utilizados por el grupo de servidores B.
    
- El servicio de SMB (TCP/445) de cada servidor Front-End del grupo de servidores B para el almacén de archivos utilizada por el grupo A.
    
> [!CAUTION]
>  IPsec no está pensado para reemplazar la seguridad de la aplicación, como SSL/TLS. Una ventaja de utilizar IPsec es que puede ofrecer seguridad de tráfico de red para las aplicaciones existentes sin necesidad de cambiarlas. Las empresas que desean proteger sólo el transporte entre los dos centros de datos deben consultar sus respectivos proveedores de hardware de red acerca de las formas para configurar las conexiones WAN seguras mediante el uso de equipamiento del proveedor.
  
## <a name="see-also"></a>Vea también

[Implementación de grupos de servidores Front-End emparejados para la recuperación ante desastres en Skype para Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md)