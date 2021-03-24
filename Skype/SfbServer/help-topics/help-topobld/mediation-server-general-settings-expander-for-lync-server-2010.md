---
title: Expansor de configuración general del servidor de mediación para Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'Las propiedades de los servidores de mediación se editan en este cuadro de diálogo. En el lazo izquierdo se encuentra un conjunto de vínculos rápidos que le llevan a la configuración general, la configuración de próximo salto y la configuración de puerta de enlace RTC. En cada sección se encuentran las siguientes opciones:'
ms.openlocfilehash: 6c8c238ce7d89db53f3b92a0f513c080976a3bab
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114196"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a>Expansor de configuración general del servidor de mediación para Lync Server 2010

Las propiedades de los servidores de mediación se editan en este cuadro de diálogo. En el lazo izquierdo se encuentra un conjunto de vínculos rápidos que le llevan a la configuración general, la configuración de próximo salto y la configuración de puerta de enlace RTC. En cada sección se encuentran las siguientes opciones:

 **General**:

- **FQDN:** edita el nombre de dominio completo del servidor de mediación

- **Asociaciones:** active la casilla Asociar grupo perimetral (para componentes **multimedia)** y seleccione un servidor perimetral o un grupo de servidores perimetrales para que el servidor de mediación lo use como ruta de acceso multimedia para el acceso externo.

  **Próximo salto**:

- **Selección del próximo** salto: seleccione en una lista el servidor front-end o el grupo de servidores front-end que se usará como ruta de acceso para que el servidor de mediación use para comunicarse con la implementación.

  **Puerta de enlace RTC**:

  **Puerta de enlace RTC del servidor de mediación**:

- **Puertos de** escucha: defina los puertos en los que escuchará el servidor de mediación. Puede definir un puerto para **TLS** o seguridad de la capa de transporte, o **TCP**, o protocolo de control de transporte. Para que la entrada de puerto de TCP esté disponible, debe seleccionar la casilla de verificación **Habilitar puerto TCP**.

    > [!IMPORTANT]
    > Consulte la documentación y los ajustes de configuración de la puerta de enlace de la red telefónica conmutada (RTC) para determinar si necesita habilitar y definir valores de puerto TLS, TCP o ambos. TLS es un protocolo más seguro, que usa certificados para cifrar el tráfico entre el servidor de mediación y la puerta de enlace RTC. No todas las puertas de enlace RTC son compatibles con TLS.

- Se muestra una lista de los troncos SIP y las puertas de enlace que se han definido y configurado para la implementación. Si no se muestra ninguna entrada, significa que no hay troncos SIP ni puertas de enlace RTC configurados para la implementación. Puede definir y configurar troncos y puertas de enlace en **Componentes compartidos** en el Generador de topologías.

## <a name="see-also"></a>Ver también

[Información general sobre los enlaces troncales SIP](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-sip-trunking)

[Opciones de implementación de la puerta de enlace RTC](/previous-versions/office/lync-server-2013/lync-server-2013-pstn-gateway-deployment-options)