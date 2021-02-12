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
description: Obtenga información sobre las consideraciones de planeación para el Sistema telefónico (PBX en la nube) con conectividad RTC local.
ms.openlocfilehash: f8baab67191f32013a9d7a01ddc12f1b04b62c03
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358816"
---
# <a name="plan-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Planear el Sistema telefónico con una conectividad RTC local en Skype Empresarial Server

> [!Important]
> Skype Empresarial Online se retirará el 31 de julio de 2021, tras lo cual el servicio ya no será accesible.  Además, ya no se admite la conectividad rtc entre su entorno local, ya sea a través de Skype Empresarial Server o Cloud Connector Edition y Skype Empresarial Online.  Obtenga información sobre cómo conectar la red de telefonía local a Teams mediante [enrutamiento directo.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

Obtenga información sobre las consideraciones de planeación para el Sistema telefónico (PBX en la nube) con conectividad RTC local.

Este contenido es relevante si ya tiene Skype Empresarial Server o Lync Server 2013 implementado localmente. Para otros escenarios, vea [soluciones de telefonía de Microsoft.](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)

 El sistema telefónico con conectividad RTC local le permite aprovechar las capacidades del Sistema telefónico (PBX en la nube) para los usuarios. Esto puede ayudar con los siguientes escenarios:

- Tiene algunos de sus usuarios de Skype Empresarial en local y otros en Skype Empresarial Online. Ahora puede habilitar las funciones y características del sistema telefónico para los usuarios que están en Skype Empresarial Online, pero seguir usando la conectividad RTC local.

- You have an on-premises deployment and you want to move some or all of your users to Skype for Business Online but continue to use on-premises PSTN connectivity.

    > [!IMPORTANT]
    > Para habilitar correctamente a los usuarios para el Sistema telefónico con conectividad RTC local, su dirección SIP debe estar en su propio dominio. El uso del dominio predeterminado para Microsoft 365 u Office 365, onmicrosoft.com, no es compatible. 

Para obtener más información sobre el Sistema telefónico, incluidas las licencias y los planes, consulte Planes de llamadas [RTC para Skype Empresarial.](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)

## <a name="feature-comparison"></a>Comparación de características

PBX en la nube con conectividad RTC local no ofrece el mismo conjunto de características que una solución de Telefonía IP empresarial local. Para ayudarle a decidir si PBX en la nube con conectividad RTC local proporcionará el conjunto de características adecuado para su organización, vea esto es lo que obtiene con PBX en [la nube.](https://go.microsoft.com/fwlink/?LinkId=715517)

## <a name="benefits-and-planning-considerations"></a>Ventajas y consideraciones de planeación

> [!CAUTION]
> Los dispositivos Lync Phone Edition DEBEN actualizarse al firmware mínimo necesario en su entorno local ANTES de pasar a Skype Empresarial Online.
Si mueve los usuarios de local a en línea antes de actualizar el firmware, los usuarios no podrán conectarse con sus teléfonos. Para corregir este problema, los usuarios deben volver al entorno local para que sus teléfonos se actualicen al firmware mínimo. NO INTENTE ACTUALIZAR AL FIRMWARE MÍNIMO NI RESTABLECER EL TELÉFONO DE FORMA AUTOMÁTICA ANTES DE VOLVER A MOVER AL USUARIO AL ENTORNO LOCAL.
Si se realiza un restablecimiento duro mientras el dispositivo no está en el firmware mínimo, se usa de forma predeterminada la autenticación de PIN, que no se admite en Skype Empresarial Online. Para obtener más información, consulte [Obtener teléfonos para Skype Empresarial Online.](https://support.office.com/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US)

Al implementar el sistema telefónico con conectividad RTC local, puede mover los usuarios a la nube a través de Skype Empresarial Online a su propio ritmo, a la vez que conserva su conectividad rtc local. Si tiene una PBX, la seguirá usando para proporcionar conectividad RTC a los usuarios que se muevan a la nube. Una vez que un usuario se mueve a Skype Empresarial Online y al Sistema telefónico, su teléfono PBX heredado ya no funcionará, pero su número de teléfono se enrutará a cualquiera de los clientes de Skype Empresarial para equipos o teléfonos inteligentes, así como teléfonos de escritorio compatibles con Skype Empresarial. Una vez que se han portado, los usuarios del sistema telefónico y los usuarios de PBX heredados pueden llamarse entre sí con normalidad, así como realizar y recibir llamadas RTC con su número de teléfono normal.

Es posible que tenga una característica personalizada o un complemento principal para su PBX heredada, como un centro de llamadas. Si la característica personalizada no está disponible actualmente en el Sistema telefónico, debe dejar a los usuarios que requieran esa característica personalizada local con la PBX heredada y simplemente porte los usuarios que no necesiten tener acceso a la característica personalizada al Sistema telefónico con conectividad RTC local.

Para obtener una lista de PBX heredadas que interoperan directamente con Skype Empresarial Server 2015, vea Infraestructura cualificada [para Microsoft Lync.](https://docs.microsoft.com/SkypeForBusiness/lync-cert/qualified-ip-pbx-gateway) Si su PBX no está en esta lista, puede usar un controlador de borde de sesión para conectar su PBX con el sistema telefónico en Skype Empresarial Online.

### <a name="network-considerations-for-quality-and-performance"></a>Consideraciones de red para la calidad y el rendimiento

Al implementar un servicio hospedado en la nube como Sistema telefónico con conectividad RTC local, debe tener en cuenta lo siguiente. En una implementación de Skype Empresarial Server 2015 Telefonía IP empresarial, toda la infraestructura y los clientes están en la propia red de la empresa. La calidad y el rendimiento de esta red, que es fundamental para audio y vídeo de alta calidad, están bajo el control directo del personal de la empresa. Con el Sistema telefónico con conectividad RTC local, hay tres redes implicadas, dos de las cuales son responsables del cliente, pero solo una de las cuales el personal de la empresa tiene control directo sobre:

- **Red global de entrega de medios de Microsoft** Infraestructura y red en la nube global de Microsoft. El tráfico y los servidores del sistema telefónico atraviesan esta red.

- **Interconexión rtc empresarial/en la nube** Se trata de la red que conecta su empresa a la nube. Esto no es necesariamente lo mismo que la conexión a Internet genérica.

- **La red de su empresa** La calidad de los medios en tiempo real depende en gran medida de tu propia red: especialmente la red WiFi y la calidad de la interconexión usada para llegar a la nube.

> [!NOTE]
> Para obtener más información sobre cómo ajustar el rendimiento en Skype Empresarial Online, vea [Ajustar el rendimiento de Skype Empresarial Online.](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US) 

## <a name="prerequisites-for-using-phone-system-with-on-premises-pstn-connectivity"></a>Requisitos previos para usar el sistema telefónico con conectividad RTC local

Antes de configurar el Sistema telefónico con conectividad RTC local y mover usuarios a Skype Empresarial Online, debe confirmar que tiene los siguientes requisitos previos:

 **Versiones de servidor local.** Las versiones de los servidores de la implementación local deben aparecer en la siguiente tabla para admitir sistema telefónico con conectividad RTC local.


| **Rol del servidor**                                       | **Versiones compatibles\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| Perímetro de federación\*\*  <br/>                            | Skype Empresarial Server 2015  <br/>                                                                              |
| Servidor de grupo interno de ruta de federación del próximo salto  <br/> | Skype Empresarial Server 2015, actualización acumulativa 6.0.9319.235 o superior de marzo de 2016 (front-end o director)  <br/> |
| Servidor de usuario front-end  <br/>                          | Skype Empresarial Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| Servidor perimetral  <br/>                                    | Skype Empresarial Server 2015  <br/>                                                                              |
| Servidor de mediación  <br/>                               | Skype Empresarial Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*Las versiones mínimas admitidas son:

- Skype Empresarial Server 2015, actualización acumulativa 6.0.9319.235 de marzo de 2016

- Actualización acumulativa 5.0.8308.920 de Lync Server 2013 de julio de 2015

\*\*La ruta de federación para todos los dominios SIP admitidos debe enrutar a través del servidor perimetral de Skype Empresarial Server 2015 que ejecuta la actualización acumulativa de marzo de 2016 o posterior. Si el grupo de usuarios está en Lync Server 2013, el tráfico del grupo externo permanece en el servidor perimetral de Lync Server 2013. 

Además, debe asegurarse de lo siguiente:

- **La configuración de Telefonía IP empresarial local se configura y se prueba para los usuarios locales** Esto incluye componentes de conectividad RTC. Para obtener más información, consulte los siguientes temas si usa Skype Empresarial Server 2015, vea [Plan for Telefonía IP empresarial in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) and Deploy Telefonía IP empresarial in Skype for Business Server [2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md).

    Si usa Lync Server 2013, consulte Planeación de Telefonía IP empresarial en [Lync Server 2013](https://technet.microsoft.com/library/gg413081%28v=ocs.15%29.aspx) e implementación de Telefonía IP empresarial en [Lync Server 2013.](https://technet.microsoft.com/library/gg412876%28v=ocs.15%29.aspx)

- **Sincronización de Active Directory** Debe configurar la sincronización de Active Directory con Azure AD Connect. Para obtener más información, vea [Administración de Azure AD Connect.](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/)

    > [!NOTE]
    > La versión de AAD Connect que use debe ser la versión 1.0.9125.0 o posterior. Si usa una versión anterior de las herramientas de AAD Connect o DirSync, actualice a la versión compatible. Puede actualizar la instalación actual y mantener las reglas personalizadas que haya definido en su entorno. 

- **Configurar la implementación híbrida** Tanto si todos los usuarios de Skype Empresarial están actualmente en línea o localmente, o si actualmente tiene una combinación, debe completar los pasos para configurar una implementación híbrida de Skype Empresarial Server o Lync Server 2013, como se describe en Implementar la conectividad híbrida entre Skype Empresarial Server y [Office 365.](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md) Para obtener más información general sobre las implementaciones híbridas, vea Planear la conectividad híbrida entre [Skype Empresarial Server y Office 365.](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) 

    Si usa Lync Server 2013, consulte [Lync Server 2013 híbrido.](https://technet.microsoft.com/library/jj204805%28v=ocs.15%29.aspx)

- **(Recomendado) Servicios de federación de Active Directory (AD FS).** Se recomienda implementar AD FS para admitir el inicio de sesión único. Para obtener más información, vea Servicios de federación [de Active Directory (AD FS).](https://technet.microsoft.com/library/cc736690%28v=ws.10%29.aspx)

Para obtener información acerca de la implementación del sistema telefónico, consulte Habilitar usuarios para el sistema telefónico con conectividad RTC [local en Skype Empresarial Server.](enable-users-for-phone-system.md)


