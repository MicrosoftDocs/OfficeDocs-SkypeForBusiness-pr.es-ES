---
title: Planear un sistema telefónico en Office 365 con conectividad RTC local en Skype empresarial Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/26/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 021a4c0b-d5de-4155-a506-650d758624aa
description: Obtenga más información sobre las consideraciones de planeación para el sistema telefónico en Office 365 (PBX en la nube) con conectividad RTC local.
ms.openlocfilehash: 1ca12d1680b56612c2e6f3a1785ee615138294ce
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221046"
---
# <a name="plan-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Planear un sistema telefónico en Office 365 con conectividad RTC local en Skype empresarial Server

Obtenga más información sobre las consideraciones de planeación para el sistema telefónico en Office 365 (PBX en la nube) con conectividad RTC local.

Este contenido es relevante si ya tiene Skype empresarial Server o Lync Server 2013 implementado de forma local. Para otros escenarios, vea [soluciones de telefonía de Microsoft](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions).

 El sistema telefónico en Office 365 con conectividad RTC local le permite aprovechar las capacidades de sistema telefónico (PBX en la nube) para sus usuarios. Esto puede resultarle útil en los escenarios siguientes:

- Tiene algunos usuarios de Skype empresarial alojados de forma local y otros que se han alojado en Skype empresarial online. Ahora puede habilitar el sistema telefónico en las características y capacidades de Office 365 para los usuarios alojados en Skype empresarial online, pero seguir usando la conectividad RTC local.

- Tiene una implementación local y desea mover algunos o todos los usuarios a Skype empresarial online, pero seguir usando la conectividad de RTC local (local).

    > [!IMPORTANT]
    > Para habilitar correctamente a los usuarios para el sistema telefónico en Office 365 con conectividad RTC local, su dirección SIP debe estar en su propio dominio. No se admite el uso del dominio predeterminado para Office 365 (onmicrosoft.com). 

Para obtener más información sobre el sistema telefónico en Office 365, incluidas las licencias y los planes, consulte [planes de llamadas RTC para Skype empresarial](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).

## <a name="feature-comparison"></a>Comparación de características

PBX en la nube con conectividad RTC local no ofrece el mismo conjunto de características que una solución de voz empresarial completa. Para ayudarle a decidir si PBX en la nube con conectividad RTC local proporcionará el conjunto de características adecuado para su organización, vea [esto es lo que obtiene con PBX en la nube](https://go.microsoft.com/fwlink/?LinkId=715517).

## <a name="benefits-and-planning-considerations"></a>Ventajas y consideraciones de planeamiento

> [!CAUTION]
> Los dispositivos de Lync Phone Edition TIENEN que estar actualizados con el firmware mínimo necesario en su entorno local ANTES de migrar a Skype Empresarial Online.
Si transfiere los usuarios desde un entorno local a un entorno en línea antes de actualizar el firmware, los usuarios no se podrán conectar con sus teléfonos. Para corregir este problema, es necesario volver a transferir los usuarios al entorno local para actualizar sus teléfonos con el firmware mínimo. NO INTENTE ACTUALIZAR AL FIRMWARE MÍNIMO O REALIZAR UN RESTABLECIMIENTO COMPLETO DEL TELÉFONO ANTES DE VOLVER A TRANSFERIR AL USUARIO A SU ENTORNO LOCAL.
Si se realiza un restablecimiento completo mientras el dispositivo no tiene instalado el firmware mínimo, se usará de forma predeterminada la autenticación con PIN, que no es compatible con Skype Empresarial Online. Para obtener más información, consulte [obtener teléfonos para Skype empresarial online](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).

Al implementar el sistema telefónico en Office 365 con conectividad RTC local, puede mover los usuarios a la nube a través de Skype empresarial online a su propio ritmo, a la vez que mantiene su conectividad RTC local. Si tiene un PBX, seguirá usándolo para proporcionar conectividad RTC a los usuarios que transfirió a la nube. Una vez que un usuario se mueve a Skype empresarial online y al sistema telefónico en Office 365, su teléfono PBX heredado dejará de funcionar, pero su número de teléfono se dirigirá a cualquiera de los clientes de Skype empresarial para PC o Smart Phone, así como al teléfono de escritorio compatible con Skype empresarial. g. Una vez que se ha migrado, el sistema telefónico de los usuarios de Office 365 y los usuarios de PBX heredados puede llamarlos normalmente, así como realizar o recibir llamadas RTC con su número de teléfono normal.

Puede tener una característica personalizada o un complemento principal en su PBX heredado, como un centro de llamadas. Si la característica personalizada no está disponible actualmente en el sistema telefónico en Office 365, debe dejar a aquellos usuarios que requieren la característica personalizada local con la PBX heredada y, simplemente, migrar los usuarios que no necesitan acceder a la característica personalizada en el sistema telefónico en Office 365 con conectividad RTC local.

Para obtener una lista de las PBX heredadas que interoperan directamente con Skype empresarial Server 2015, consulte [infraestructura cualificada para Microsoft Lync](https://docs.microsoft.com/SkypeForBusiness/lync-cert/qualified-ip-pbx-gateway). Si su PBX no está en esta lista, puede usar un controlador de borde de sesión para conectar su PBX con el sistema telefónico en Office 365 en Skype empresarial online.

### <a name="network-considerations-for-quality-and-performance"></a>Consideraciones de red para calidad y rendimiento

Al implementar un servicio hospedado en la nube como sistema telefónico en Office 365 con conectividad RTC local, debe tener en cuenta lo siguiente. En una implementación de voz de Skype empresarial Server 2015 puramente local, toda la infraestructura y los clientes están en la propia red de la empresa. La calidad y el rendimiento de esta red, que son críticos para un audio y vídeo de alta calidad, se encuentran controlados directamente por el personal de la empresa. Con el sistema telefónico de Office 365 con conectividad RTC local, hay tres redes involucradas, dos de las cuales el cliente es responsable pero solo una de las cuales el personal de la empresa tiene control directo sobre:

- **Red de entrega global de multimedia de Microsoft** La infraestructura y la red de nube global de Microsoft. Office 365 y el sistema telefónico en los servidores de Office 365 y el tráfico atraviesa esta red.

- **Interconexión RTC de empresa/nube** Esta es la red que conecta su empresa con la nube de Office 365. Esto no es necesariamente el mismo que tu conexión a Internet genérica.

- **Su propia red empresarial** La calidad de los medios en tiempo real depende en gran medida de su propia red: especialmente de la red WiFi y de la calidad de la interconexión utilizada para llegar a la nube de Office 365.

> [!NOTE]
> Para obtener más información sobre cómo ajustar el rendimiento en Skype empresarial online, consulte [ajustar el rendimiento de Skype empresarial online](https://support.office.com/en-us/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US). 

## <a name="prerequisites-for-using-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>Requisitos previos para usar el sistema telefónico en Office 365 con conectividad RTC local

Antes de configurar el sistema telefónico en Office 365 con conectividad RTC local y mover usuarios a Skype empresarial online, debe confirmar que tiene los siguientes requisitos previos:

 **Versiones de servidor local.** Las versiones de los servidores de la implementación local deben figurar en la tabla siguiente para admitir el sistema telefónico en Office 365 con conectividad RTC local.


| **Rol de servidor**                                       | **Versiones compatibles\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| Perimetral de Federación\*\*  <br/>                            | Skype Empresarial Server 2015  <br/>                                                                              |
| Servidor del grupo interno de ruta de federación del próximo salto  <br/> | Skype Empresarial Server 2015, actualización acumulativa 6.0.9319.235 de marzo de 2016 o superior (front-end o Director)   <br/> |
| Servidor de usuario front-end  <br/>                          | Skype Empresarial Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| Servidor perimetral  <br/>                                    | Skype Empresarial Server 2015  <br/>                                                                              |
| Servidor de mediación  <br/>                               | Skype Empresarial Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*Las versiones mínimas admitidas son las siguientes:

- Skype Empresarial Server 2015, actualización acumulativa 6.0.9319.235 de marzo de 2016

- Lync Server 2013, actualización acumulativa 5.0.8308.920 de julio de 2015

\*\*La ruta de Federación para todos los dominios SIP compatibles debe enrutar a través del servidor perimetral de Skype empresarial Server 2015 que ejecuta la actualización acumulativa de marzo de 2016 de marzo. Si el grupo de usuarios está en Lync Server 2013, ese tráfico de grupo externo permanece en el servidor perimetral de Lync Server 2013. 

Además, debe asegurarse de lo siguiente:

- **La telefonía IP empresarial local está configurada y probada para usuarios locales** Esto incluye los componentes de conectividad RTC. Para obtener más información, consulte los siguientes temas si está usando Skype empresarial Server 2015, consulte [Plan for Enterprise Voice en Skype empresarial server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) e implantar [telefonía IP empresarial en skype empresarial Server 2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md).

    Si usa Lync Server 2013, consulte [planificación de telefonía empresarial en Lync server 2013](https://technet.microsoft.com/library/gg413081%28v=ocs.15%29.aspx) e implementación de [telefonía IP empresarial en Lync Server 2013](https://technet.microsoft.com/EN-US/library/gg412876%28v=ocs.15%29.aspx).

- **Sincronización de Active** Directory Debe configurar la sincronización de Active Directory con Azure AD Connect. Para obtener más información, consulte [Managing Azure ad Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/).

    > [!NOTE]
    > La versión de AAD Connect que use tiene que ser la versión 1.0.9125.0 o posterior. Si usa una versión anterior de las herramientas de AAD Connect o DirSync, actualice a la versión compatible. Puede actualizar la instalación actual y mantener las reglas personalizadas que haya definido en su entorno. 

- **Configurar la implementación híbrida** Ya sea que todos los usuarios de Skype empresarial estén alojados en línea o estén locales, o si actualmente tiene una combinación, debe completar los pasos para configurar una implementación híbrida de Skype empresarial Server o Lync Server 2013, tal como se describe en [implementar híbrido conectividad entre Skype empresarial Server y Office 365](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md). Para obtener más información general sobre las implementaciones híbridas, consulte [planear la conectividad híbrida entre Skype empresarial Server y Office 365](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json). 

    Si usa Lync Server 2013, vea [Lync server 2013 híbrido](https://technet.microsoft.com/EN-US/library/jj204805%28v=ocs.15%29.aspx).

- **Práctica Servicios de Federación de Active Directory (AD FS).** Se recomienda implementar AD FS para que admita el inicio de sesión único. Para obtener más información, vea [servicios de Federación de Active Directory (AD FS)](https://technet.microsoft.com/en-us/library/cc736690%28v=ws.10%29.aspx).

Para obtener más información sobre cómo implementar el sistema telefónico en Office 365, consulte [Habilitar usuarios para el sistema telefónico en office 365 con conectividad RTC local en Skype empresarial Server](enable-users-for-phone-system.md).


