---
title: Expansor de configuración General del servidor de mediación para Lync Server 2010
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'Para editar las propiedades de los servidores de mediación en este cuadro de diálogo. En el lado izquierdo es un conjunto de vínculos rápidos para pasar a la configuración para la configuración General, la configuración de próximo salto y la configuración de puerta de enlace de RTC. En cada sección son las siguientes opciones:'
ms.openlocfilehash: 262cdcbbbf4c4cfcf35a01de91c88c6511da3360
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23260478"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a>Expansor de configuración General del servidor de mediación para Lync Server 2010

Para editar las propiedades de los servidores de mediación en este cuadro de diálogo. En el lado izquierdo es un conjunto de vínculos rápidos para pasar a la configuración para la configuración General, la configuración de próximo salto y la configuración de puerta de enlace de RTC. En cada sección son las siguientes opciones:

 **General**:

- **FQDN**: edite el nombre de dominio completo del servidor de mediación

- **Asociaciones**: Active la casilla de verificación de **grupo de servidores perimetrales asociados (para componentes multimedia)** y seleccione un servidor perimetral o grupo de servidores perimetrales para el servidor de mediación para usarlo como la ruta de acceso de medios para el acceso externo.

 **Próximo salto**:

- **Selección de próximo salto**: seleccione en la lista el grupo de servidores Front-End o de servidor Front-End para usarlo como la ruta de acceso para el servidor de mediación que se usará para comunicarse con su implementación.

 **Puerta de enlace RTC**:

 **Puerta de enlace RTC del servidor de mediación**:

- **Puertos de escucha**: definir los puertos de escucha en el servidor de mediación. Puede definir un puerto para la seguridad de la capa de transporte o de **TLS** o **TCP**, o protocolo de control de transporte. Para el puerto de entrada para TCP para que esté disponible, debe seleccionar la casilla de verificación para **Habilitar el puerto TCP**.

    > [!IMPORTANT]
    > Hacer referencia a la configuración de documentación y la configuración de la puerta de enlace de telefónica conmutada (RTC) para determinar si necesita habilitar y definir valores de puerto TLS, TCP o ambos. TLS es un protocolo más seguro, uso de certificados para cifrar el tráfico entre el servidor de mediación y la puerta de enlace de RTC. No todas las puertas de enlace de RTC admiten TLS.

- Aparece una lista de enlaces troncales SIP y las puertas de enlace que se definen y configurados para su implementación. Si no hay entradas están presentes, no hay ningún troncos SIP o puertas de enlace RTC configurados para su implementación. Definir y configurar troncos y las puertas de enlace en **Componentes compartidos** en el generador de topología.

## <a name="see-also"></a>Vea también

[Información general sobre el enlace troncal SIP](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[Opciones de implementación de puerta de enlace de RTC](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)