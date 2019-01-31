---
title: Planear el sistema telefónico en Office 365 con conectividad de RTC local en Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/26/2018
ms.audience: ITPro
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
description: Obtenga información acerca de las consideraciones de planeación para el sistema telefónico en Office 365 (en la nube PBX) con conectividad de RTC local.
ms.openlocfilehash: 978da546961188c54c7e08e2ed140f8d01986e44
ms.sourcegitcommit: 20defe18ac1d2b21853bd6d5f0772cd3f35e53e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2019
ms.locfileid: "29686475"
---
# <a name="plan-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Planear el sistema telefónico en Office 365 con conectividad de RTC local en Skype para Business Server

Obtenga información acerca de las consideraciones de planeación para el sistema telefónico en Office 365 (en la nube PBX) con conectividad de RTC local.

Este contenido es relevante si ya dispone de Skype para Business Server o Lync Server 2013 implementado localmente. Para otros escenarios, consulte [soluciones de telefonía de Microsoft](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions).

 Sistema telefónico en Office 365 con conectividad de RTC local le permite aprovechar las capacidades de sistema telefónico (PBX en la nube) para los usuarios. Esto puede resultarle útil en los escenarios siguientes:

- Tiene algunas de su Skype para empresarial a los usuarios hospedados en implementaciones locales y otros usuarios hospedados en Skype para profesionales en línea. Ahora puede habilitar sistema telefónico en Office 365 capacidades y características para los usuarios alojados en Skype para profesionales en línea, pero seguirán usando conectividad con RTC local.

- Tiene una implementación local y que desea mover algunos o todos los usuarios a Skype para profesionales en línea pero seguir usando conectividad con RTC local.

    > [!IMPORTANT]
    > Para habilitar correctamente a los usuarios para el sistema telefónico en Office 365 con conectividad de RTC local, debe ser su dirección SIP en su propio dominio. No se admite el uso del dominio predeterminado para Office 365 (onmicrosoft.com). 

Para obtener más información acerca del sistema de teléfono en Office 365, incluida la concesión de licencias y planes de, vea [los planes de RTC de llamada de Skype para la empresa](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).

## <a name="feature-comparison"></a>Comparación de características

En la nube PBX con conectividad de RTC local no ofrece el mismo conjunto como una solución de Enterprise Voice totalmente local de características. Para ayudarle a decidir si PBX en la nube con conectividad de RTC local proporcionará el derecho conjunto de características de la organización, vea [aquí es lo que obtiene con PBX en la nube](https://go.microsoft.com/fwlink/?LinkId=715517).

## <a name="benefits-and-planning-considerations"></a>Ventajas y consideraciones de planeamiento

> [!CAUTION]
> Los dispositivos de Lync Phone Edition TIENEN que estar actualizados con el firmware mínimo necesario en su entorno local ANTES de migrar a Skype Empresarial Online.
Si transfiere los usuarios desde un entorno local a un entorno en línea antes de actualizar el firmware, los usuarios no se podrán conectar con sus teléfonos. Para corregir este problema, es necesario volver a transferir los usuarios al entorno local para actualizar sus teléfonos con el firmware mínimo. NO INTENTE ACTUALIZAR AL FIRMWARE MÍNIMO O REALIZAR UN RESTABLECIMIENTO COMPLETO DEL TELÉFONO ANTES DE VOLVER A TRANSFERIR AL USUARIO A SU ENTORNO LOCAL.
Si se realiza un restablecimiento completo mientras el dispositivo no tiene instalado el firmware mínimo, se usará de forma predeterminada la autenticación con PIN, que no es compatible con Skype Empresarial Online. Para obtener más información, consulte [Introducción teléfonos de Skype para profesionales en línea](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).

Mediante la implementación del sistema de teléfono en Office 365 con conectividad de RTC local, puede mover los usuarios a la nube a través de Skype para profesionales en línea a su propio ritmo, conservando su conectividad de RTC local. Si tiene un PBX, seguirá usándolo para proporcionar conectividad RTC a los usuarios que transfirió a la nube. Una vez que un usuario se mueve a Skype para profesionales en línea y el sistema de teléfono en Office 365, dejará de funcionar su teléfono PBX heredado, pero su número de teléfono redirigirá a cualquiera de los Skype para clientes empresariales de PC o teléfonos inteligentes, así como Skype para teléfono de escritorio compatibles con el negocio s. Una vez que los puertos, sistema telefónico en Office 365 a los usuarios y los usuarios de PBX heredados puede llamar mutuamente normalmente así como realizar y recibir llamadas de RTC mediante su número de teléfono normal.

Puede tener una característica personalizada o un complemento principal en su PBX heredado, como un centro de llamadas. Si la característica personalizada no está actualmente disponible en el sistema telefónico en Office 365, debe dejar aquellos usuarios que requieren esa característica personalizada local con el sistema PBX heredado y el puerto sólo los usuarios que no es necesario para tener acceso a la característica personalizada para el sistema telefónico en Office 365 con la conectividad de RTC local.

Para obtener una lista de PBX heredadas que interoperar directamente con Skype para Business Server 2015 vea [Infraestructura completa para Microsoft Lync](https://docs.microsoft.com/SkypeForBusiness/lync-cert/qualified-ip-pbx-gateway). Si su PBX no está en esta lista, puede usar un controlador de borde de sesión para conectar su PBX con el sistema telefónico en Office 365 en Skype para profesionales en línea.

### <a name="network-considerations-for-quality-and-performance"></a>Consideraciones de red para calidad y rendimiento

Al implementar un servicio hospedada en la nube como sistema telefónico en Office 365 con conectividad de RTC local, debe tenga en cuenta lo siguiente. En un Skype puramente local para la implementación de Enterprise Voice de Business Server 2015, la infraestructura y los clientes se encuentran en la red de la empresa. La calidad y el rendimiento de esta red, que son críticos para un audio y vídeo de alta calidad, se encuentran controlados directamente por el personal de la empresa. Con el sistema telefónico en Office 365 con conectividad de RTC local, hay tres redes implicados, dos de los cuales el cliente es responsable de pero sólo uno de los cuales el personal de la empresa tiene control directo a través de:

- **Red de entrega de medios Global de Microsoft** Red global en la nube y una infraestructura de Microsoft. Office 365 y el sistema de teléfono en el tráfico y los servidores de Office 365 atraviesan esta red.

- **Interconnect Enterprise RTC y en la nube** Ésta es la red que se conecta a su empresa a la nube de Office 365. Esto no es necesariamente el mismo que su conexión a Internet genérica.

- **La red de la empresa** La calidad de los medios en tiempo real depende en gran medida su propia red: especialmente la red WiFi y la calidad de la interconexión utilizada para llegar a la nube de Office 365.

> [!NOTE]
> Para obtener más información sobre el rendimiento de ajuste en Skype para profesionales en línea, vea [Optimización de Skype para obtener un rendimiento empresarial en línea](https://support.office.com/en-us/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US). 

## <a name="prerequisites-for-using-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>Requisitos previos para usar el sistema telefónico en Office 365 con conectividad de RTC local

Antes de poder configurar el sistema telefónico en Office 365 con conectividad de RTC local y mover usuarios a Skype para profesionales en línea, debe confirmar que dispone de los siguientes requisitos previos en su lugar:

 **Versiones de servidor local.** Las versiones de los servidores de la implementación local deben aparecer en la tabla siguiente para admitir el sistema telefónico en Office 365 con conectividad de RTC local.


| **Rol de servidor**                                       | **Versiones compatibles\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| Borde de federación\*\*  <br/>                            | Skype Empresarial Server 2015  <br/>                                                                              |
| Servidor del grupo interno de ruta de federación del próximo salto  <br/> | Skype Empresarial Server 2015, actualización acumulativa 6.0.9319.235 de marzo de 2016 o superior (front-end o Director)   <br/> |
| Servidor de usuario front-end  <br/>                          | Skype Empresarial Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| Servidor perimetral  <br/>                                    | Skype Empresarial Server 2015  <br/>                                                                              |
| Servidor de mediación  <br/>                               | Skype Empresarial Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*Mínimo de las versiones compatibles son:

- Skype Empresarial Server 2015, actualización acumulativa 6.0.9319.235 de marzo de 2016

- Lync Server 2013, actualización acumulativa 5.0.8308.920 de julio de 2015

\*\*La federación de ruta para todos los dominios SIP admitidos deben enrutar a través de la Skype para ejecución de servidor perimetral de Business Server 2015 actualización acumulativa de la actualización de marzo 2016 o superior. Si el grupo de usuarios está en Lync Server 2013, ese tráfico de grupo externo permanece en el servidor perimetral de Lync Server 2013. 

Además debe asegurarse de lo siguiente:

- **Telefonía IP empresarial local está configurado y probado para usuarios locales** Esto incluye los componentes de conectividad de RTC. Para obtener más información, vea los temas siguientes si usa Skype para Business Server 2015, vea [planear para Enterprise Voice en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) y la [Implementación de Enterprise Voice en Skype para Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md).

    Si está utilizando Lync Server 2013, consulte [Planning for Enterprise Voice en Lync Server 2013](https://technet.microsoft.com/library/gg413081%28v=ocs.15%29.aspx) y la [Implementación de Enterprise Voice en Lync Server 2013](https://technet.microsoft.com/EN-US/library/gg412876%28v=ocs.15%29.aspx).

- **Sincronización de Active Directory** Debe configurar la sincronización de Active Directory con Azure Connect de AD. Para obtener más información, vea [administración de Azure AD conectar](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/).

    > [!NOTE]
    > La versión de AAD Connect que use tiene que ser la versión 1.0.9125.0 o posterior. Si usa una versión anterior de las herramientas de AAD Connect o DirSync, actualice a la versión compatible. Puede actualizar la instalación actual y mantener las reglas personalizadas que haya definido en su entorno. 

- **Configure su implementación híbrida** Si todos su Skype para usuarios profesionales actualmente están hospedados ya sea en línea o local, o si tiene actualmente una combinación, debe completar los pasos para configurar una implementación híbrida de Skype para Business Server o Lync Server 2013, tal como se describe en [implementación híbrida conectividad entre Skype para Business Server y Office 365](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md). Para obtener más información de fondo en las implementaciones híbridas, consulte [Plan de conectividad híbrida entre Skype para Business Server y Office 365](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md). 

    Si está utilizando Lync Server 2013, consulte [Lync Server 2013 hybrid](https://technet.microsoft.com/EN-US/library/jj204805%28v=ocs.15%29.aspx).

- **Servicios de federación de Active Directory (AD FS) (recomendado)** Se recomienda implementar AD FS para admitir Single Sign-on. Para obtener más información, vea [Servicios de federación de Active Directory (AD FS)](https://technet.microsoft.com/en-us/library/cc736690%28v=ws.10%29.aspx).

Para obtener información acerca de la implementación del sistema de teléfono en Office 365, consulte [configuración de sistema de teléfono de la organización](https://docs.microsoft.com/en-us/microsoftteams/setting-up-your-phone-system?toc=/skypeforbusiness/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).


