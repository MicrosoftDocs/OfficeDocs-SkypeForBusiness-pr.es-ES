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
description: 'Las propiedades de los servidores de mediación se modifican en este cuadro de diálogo. En el lazo izquierdo se encuentra un conjunto de vínculos rápidos que le llevan a la configuración general, la configuración de próximo salto y la configuración de puerta de enlace RTC. En cada sección se encuentran las siguientes opciones:'
ms.openlocfilehash: db7964826a50f462435769d66ddfab3804462541
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806750"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a>Expansor de configuración general del servidor de mediación para Lync Server 2010

Las propiedades de los servidores de mediación se modifican en este cuadro de diálogo. En el lazo izquierdo se encuentra un conjunto de vínculos rápidos que le llevan a la configuración general, la configuración de próximo salto y la configuración de puerta de enlace RTC. En cada sección se encuentran las siguientes opciones:

 **General:**

- **FQDN:** edite el nombre de dominio completo del servidor de mediación

- **Asociaciones:** active la casilla Asociar grupo de servidores perimetrales (para componentes **multimedia)** y seleccione un servidor perimetral o un grupo de servidores perimetrales para que el servidor de mediación lo use como ruta de acceso multimedia para el acceso externo.

  **Próximo salto**:

- **Selección del próximo salto:** seleccione en una lista el servidor front-end o el grupo de servidores front-end que se usará como ruta de acceso para el servidor de mediación que se usará para comunicarse con la implementación.

  **Puerta de enlace RTC**:

  **Puerta de enlace RTC del servidor de mediación**:

- **Puertos de escucha:** defina los puertos en los que escuchará el servidor de mediación. Puede definir un puerto para **TLS** o seguridad de la capa de transporte, o **TCP**, o protocolo de control de transporte. Para que la entrada de puerto de TCP esté disponible, debe seleccionar la casilla de verificación **Habilitar puerto TCP**.

    > [!IMPORTANT]
    > Consulte la documentación y los ajustes de configuración de la puerta de enlace de la red telefónica conmutada (RTC) para determinar si necesita habilitar y definir valores de puerto TLS, TCP o ambos. TLS es un protocolo más seguro, que usa certificados para cifrar el tráfico entre el servidor de mediación y la puerta de enlace RTC. No todas las puertas de enlace RTC son compatibles con TLS.

- Se muestra una lista de los troncos SIP y las puertas de enlace que se han definido y configurado para la implementación. Si no se muestra ninguna entrada, significa que no hay troncos SIP ni puertas de enlace RTC configurados para la implementación. Puede definir y configurar troncos y puertas de enlace en **Componentes compartidos** en el Generador de topologías.

## <a name="see-also"></a>Vea también

[Información general sobre los enlaces troncales SIP](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[Opciones de implementación de la puerta de enlace RTC](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
