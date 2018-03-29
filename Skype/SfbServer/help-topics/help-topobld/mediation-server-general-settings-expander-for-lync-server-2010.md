---
title: Ampliador de configuración General del servidor de mediación de Lync Server 2010
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'Editar las propiedades de los servidores de mediación en este cuadro de diálogo. En el lado izquierdo es un conjunto de vínculos rápidos para pasar a la configuración de opciones generales, ajustes de salto siguiente y configuración de puerta de enlace PSTN. En cada sección son los siguientes valores:'
ms.openlocfilehash: bc5016c9dbeb6b0693444f930c9883b1736258d2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a>Ampliador de configuración General del servidor de mediación de Lync Server 2010
 
Editar las propiedades de los servidores de mediación en este cuadro de diálogo. En el lado izquierdo es un conjunto de vínculos rápidos para pasar a la configuración de opciones generales, ajustes de salto siguiente y configuración de puerta de enlace PSTN. En cada sección son los siguientes valores:
  
 **General**:
  
- **FQDN**: editar el nombre de dominio completo del servidor de mediación
    
- **Asociaciones**: Active la casilla de verificación de **grupo de asociar borde (para componentes de medios)** y seleccione un servidor perimetral o grupo de borde para el servidor de mediación para utilizar como la ruta de acceso de medios de acceso externo.
    
 **Próximo salto**:
  
- **Selección de salto siguiente**: seleccionar de una lista que utilice como la ruta de acceso para el servidor de mediación a utilizar para la comunicación con la implementación, el grupo de servidor Front-End o Front-End.
    
 **Puerta de enlace PSTN**:
  
 **Puerta de enlace PSTN del servidor de mediación**:
  
- **Puertos de escucha**: definir los puertos de escucha en el servidor de mediación. Puede definir un puerto para la seguridad de la capa de transporte o **TLS** o **TCP**, o protocolo de control de transporte. Para la entrada de puerto para TCP esté disponible, debe seleccionar la casilla de verificación para **Habilitar el puerto TCP**. 
    
    > [!IMPORTANT]
    > Consulte la configuración de configuración y documentación de la puerta de enlace de telefónica pública conmutada (PSTN) de red para determinar si necesita habilitar y definir los valores de puerto TLS, TCP o ambos. TLS es un protocolo más seguro, el uso de certificados para cifrar el tráfico entre el servidor de mediación y la puerta de enlace PSTN. No todas las puertas de enlace PSTN compatible con TLS. 
  
- Se muestra una lista de los troncos SIP y las puertas de enlace que se definen y configurados para su implementación. Si no hay entradas están presentes, no hay ningún SIP troncos o puertas de enlace PSTN configurados para su implementación. Definir y configurar los troncos y puertas de enlace en **Componentes compartidos** en el generador de topología.
    
## <a name="see-also"></a>Vea también

#### 

[Información general acerca de SIP Trunking](http://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)
  
[Opciones de implementación de puerta de enlace PSTN](http://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)

