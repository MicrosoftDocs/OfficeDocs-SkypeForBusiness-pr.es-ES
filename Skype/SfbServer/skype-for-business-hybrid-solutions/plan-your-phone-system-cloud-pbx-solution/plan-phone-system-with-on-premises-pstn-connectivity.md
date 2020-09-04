---
title: Planear el Sistema telefónico con una conectividad RTC local en Skype Empresarial Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/26/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 021a4c0b-d5de-4155-a506-650d758624aa
description: Obtenga información sobre las consideraciones de planeación para el sistema telefónico (PBX en la nube) con conectividad con RTC local.
ms.openlocfilehash: f8baab67191f32013a9d7a01ddc12f1b04b62c03
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358816"
---
# <a name="plan-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Planear el Sistema telefónico con una conectividad RTC local en Skype Empresarial Server

> [!Important]
> Skype empresarial online se retirará el 31 de julio de 2021 después del cual el servicio ya no será accesible.  Además, la conectividad con RTC entre su entorno local, ya sea a través de Skype empresarial Server o Cloud Connector Edition y Skype empresarial online, ya no será compatible.  Obtenga información sobre cómo conectar su red de telefonía local a Microsoft Teams con [enrutamiento directo](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).

Obtenga información sobre las consideraciones de planeación para el sistema telefónico (PBX en la nube) con conectividad con RTC local.

Este contenido es relevante si ya ha implementado Skype empresarial Server o Lync Server 2013 de forma local. Para otros escenarios, vea [soluciones de telefonía de Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions).

 Sistema telefónico con conectividad con RTC local le permite aprovechar las capacidades del sistema telefónico (PBX en la nube) para sus usuarios. Esto puede ayudar en los siguientes escenarios:

- Tiene algunos de sus usuarios de Skype empresarial hospedados de forma local y otros alojados en Skype empresarial online. Ahora puede habilitar funciones y características de sistema telefónico para los usuarios alojados en Skype empresarial online, pero seguir usando la conectividad con RTC local.

- Tiene una implementación local y desea mover algunos o todos los usuarios a Skype empresarial online, pero seguir usando la conectividad con RTC local de.

    > [!IMPORTANT]
    > Para habilitar correctamente a los usuarios para el sistema telefónico con conectividad RTC local, su dirección SIP debe estar en su propio dominio. No se admite el uso del dominio predeterminado para Microsoft 365 o Office 365, onmicrosoft.com. 

Para obtener más información acerca del sistema telefónico, incluidas las licencias y los planes, consulte [planes de llamadas RTC para Skype empresarial](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).

## <a name="feature-comparison"></a>Comparación de características

PBX en la nube con conectividad con RTC local no ofrece el mismo conjunto de características que una solución de telefonía IP empresarial completa. Para ayudarle a decidir si PBX en la nube con conectividad RTC local proporcionará el conjunto de características adecuado para su organización, vea [esto es lo que obtiene con PBX en la nube](https://go.microsoft.com/fwlink/?LinkId=715517).

## <a name="benefits-and-planning-considerations"></a>Ventajas y consideraciones de planeación

> [!CAUTION]
> Los dispositivos Lync Phone Edition deben actualizarse al firmware mínimo necesario en su entorno local antes de pasar a Skype empresarial online.
Si mueve los usuarios de local a en línea antes de actualizar el firmware, los usuarios no podrán conectarse mediante sus teléfonos. Para corregir este problema, es necesario volver a mover a los usuarios al entorno local para actualizar sus teléfonos con el firmware mínimo. NO INTENTE ACTUALIZAR AL FIRMWARE MÍNIMO O REALIZAR UN RESTABLECIMIENTO RÍGIDO DEL TELÉFONO ANTES DE VOLVER A MOVER AL USUARIO A SU ENTORNO LOCAL.
Si se realiza un restablecimiento de hardware mientras el dispositivo no tiene el firmware mínimo, se usará la autenticación de PIN predeterminada, que no es compatible con Skype empresarial online. Para obtener más información, consulte [obtener teléfonos con Skype empresarial online](https://support.office.com/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).

Mediante la implementación de sistema telefónico con conectividad con RTC local, puede mover a los usuarios a la nube a través de Skype empresarial online a su propio ritmo, a la vez que mantiene su conectividad con RTC local. Si tiene una PBX, puede seguir utilizándola para proporcionar conectividad RTC a los usuarios que se mueven a la nube. Una vez que un usuario se mueve a Skype empresarial online y al sistema telefónico, su teléfono PBX heredado dejará de funcionar, pero su número de teléfono se enrutará a cualquiera de los clientes de Skype empresarial para PC o Smart Phone, así como teléfonos de escritorio compatibles con Skype empresarial. Una vez que se hayan trasladado, los usuarios de sistema telefónico y los usuarios de PBX heredados podrán llamarse entre ellos normalmente, así como realizar y recibir llamadas RTC con su número de teléfono normal.

Puede tener una característica personalizada o un complemento principal para su PBX heredada, como un centro de llamadas. Si la característica personalizada no está disponible actualmente en el sistema telefónico, debe dejar a los usuarios que requieran la característica personalizada local con la PBX heredada y simplemente portar a los usuarios que no necesitan tener acceso a la característica personalizada en el sistema telefónico con conectividad con RTC local.

Para obtener una lista de PBX heredadas que interoperen directamente con Skype empresarial Server 2015 consulte  [Infrastructure Qualified for Microsoft Lync](https://docs.microsoft.com/SkypeForBusiness/lync-cert/qualified-ip-pbx-gateway). Si su PBX no se encuentra en esta lista, puede usar un controlador de borde de sesión para conectar su PBX con sistema telefónico en Skype empresarial online.

### <a name="network-considerations-for-quality-and-performance"></a>Consideraciones de red para la calidad y el rendimiento

Al implementar un servicio hospedado en la nube como sistema telefónico con conectividad RTC local, debe tener en cuenta lo siguiente. En una implementación de Skype empresarial Server 2015 Enterprise Voice exclusivamente local, toda la infraestructura y los clientes se encuentran en la propia red de la empresa. La calidad y el rendimiento de esta red, que es fundamental para el audio y el vídeo de alta calidad, se encuentran bajo el control directo del personal de la empresa. Con el sistema telefónico con conectividad con RTC local, hay tres redes implicadas, dos de las cuales el cliente es responsable pero solo una de las cuales el personal de la empresa tiene control directo:

- **Red de entrega global de medios de Microsoft** La infraestructura y la red en la nube global de Microsoft. El tráfico y los servidores del sistema de teléfono atraviesan esta red.

- **Interconexión con RTC de empresa/nube** Esta es la red que conecta la empresa a la nube. Esto no es necesariamente el mismo que su conexión a Internet genérica.

- **La red de su empresa** La calidad de los medios en tiempo real depende en gran medida de su propia red: en especial de la red WiFi y de la calidad de la interconexión utilizada para llegar a la nube.

> [!NOTE]
> Para obtener más información sobre el ajuste del rendimiento en Skype empresarial online, consulte [ajustar el rendimiento de Skype empresarial online](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US). 

## <a name="prerequisites-for-using-phone-system-with-on-premises-pstn-connectivity"></a>Requisitos previos para usar sistema telefónico con conectividad RTC local

Antes de configurar el sistema telefónico con la conectividad con RTC local y mover usuarios a Skype empresarial online, debe confirmar que ha implementado los siguientes requisitos previos:

 **Versiones de servidor local.** Las versiones de los servidores en su implementación local deben incluirse en la lista de la tabla siguiente para admitir el sistema telefónico con conectividad con RTC local.


| **Rol del servidor**                                       | **Versiones compatibles\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| Servidor perimetral de Federación\*\*  <br/>                            | Skype Empresarial Server 2015  <br/>                                                                              |
| Servidor de grupo interno de enrutamiento de Federación de próximo salto  <br/> | Skype empresarial Server 2015, actualización acumulativa de marzo de 2016 6.0.9319.235 o superior (front-end o director)  <br/> |
| Servidor de usuario front-end  <br/>                          | Skype Empresarial Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| Servidor perimetral  <br/>                                    | Skype Empresarial Server 2015  <br/>                                                                              |
| Servidor de mediación  <br/>                               | Skype Empresarial Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*Las versiones mínimas admitidas son:

- Skype empresarial Server 2015, actualización acumulativa de marzo de 2016 6.0.9319.235

- Lync Server 2013 de julio de 2015 de la actualización acumulativa de 5.0.8308.920

\*\*La ruta de Federación para todos los dominios SIP admitidos debe enrutar a través del servidor perimetral de Skype empresarial Server 2015 que ejecuta la actualización acumulativa de marzo de 2016 o superior. Si el grupo de usuarios está en Lync Server 2013, el tráfico del grupo externo permanece en el servidor perimetral de Lync Server 2013. 

Además, debe asegurarse de lo siguiente:

- **La telefonía IP empresarial local está configurada y probada para los usuarios locales** Esto incluye los componentes de conectividad con RTC. Para obtener más información, consulte los siguientes temas si usa Skype empresarial Server 2015, consulte [Plan for Enterprise Voice in Skype for Business server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) e [deploy Enterprise Voice in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md).

    Si usa Lync Server 2013, consulte [Planning for Enterprise Voice in Lync server 2013](https://technet.microsoft.com/library/gg413081%28v=ocs.15%29.aspx) e [Deploying Enterprise Voice in Lync Server 2013](https://technet.microsoft.com/library/gg412876%28v=ocs.15%29.aspx).

- **Sincronización de Active** Directory Debe configurar la sincronización de Active Directory mediante Azure AD Connect. Para obtener más información, consulte [Managing Azure ad Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/).

    > [!NOTE]
    > La versión de AAD Connect que use debe ser la versión 1.0.9125.0 o posterior. Si usa una versión anterior de las herramientas de AAD Connect o DirSync, actualice a la versión compatible. Puede actualizar su instalación actual y mantener las reglas personalizadas que haya definido en su entorno. 

- **Configurar la implementación híbrida** Tanto si todos los usuarios de Skype empresarial están hospedados actualmente en línea como locales, o si actualmente tiene una mezcla, debe completar los pasos para configurar una implementación híbrida de Skype empresarial Server o Lync Server 2013, tal como se describe en [deploy Hybrid Connectivity between Skype for Business Server y Office 365](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md). Para más información general sobre las implementaciones híbridas, vea [plan Hybrid Connectivity between Skype for Business Server y Office 365](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json). 

    Si usa Lync Server 2013, consulte [Lync server 2013 Hybrid](https://technet.microsoft.com/library/jj204805%28v=ocs.15%29.aspx).

- **Recomenda Servicios de Federación de Active Directory (AD FS).** Se recomienda implementar AD FS para que admita el inicio de sesión único. Para obtener más información, vea [servicios de Federación de Active Directory (AD FS)](https://technet.microsoft.com/library/cc736690%28v=ws.10%29.aspx).

Para obtener información acerca de la implementación de sistema telefónico, consulte [Habilitar usuarios para sistema telefónico con conectividad con RTC local en Skype empresarial Server](enable-users-for-phone-system.md).


