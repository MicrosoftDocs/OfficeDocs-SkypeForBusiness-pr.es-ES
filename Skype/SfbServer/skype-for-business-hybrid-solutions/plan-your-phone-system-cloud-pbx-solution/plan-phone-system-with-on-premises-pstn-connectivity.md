---
title: Sistema de teléfono del plan en Office 365 con conectividad de RTC local en Skype para Business Server
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
ms.custom: Strat_SB_Hybrid
ms.assetid: 021a4c0b-d5de-4155-a506-650d758624aa
description: Obtenga información acerca de las consideraciones de diseño para el sistema de teléfono en Office 365 (nube PBX) con conectividad de RTC local.
ms.openlocfilehash: 5b244ea55305d88cc214875dc74837f027cc3dd5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Sistema de teléfono del plan en Office 365 con conectividad de RTC local en Skype para Business Server
 
Obtenga información acerca de las consideraciones de diseño para el sistema de teléfono en Office 365 (nube PBX) con conectividad de RTC local.
  
Este contenido es importante si ya tienes Skype para Business Server o Lync Server 2013 implementado local. Para otros escenarios, vea [Planear el sistema de teléfono en la solución de Office 365 (nube PBX)](plan-your-phone-system-cloud-pbx-solution.md).
  
 Sistema de teléfono en Office 365 con conectividad de RTC local le permite aprovechar las capacidades del sistema telefónico (PBX nube) para los usuarios. Esto puede resultarle útil en los escenarios siguientes:
  
- Tiene algunas de su Skype para los usuarios alojados en-locales comerciales y otras personas alojadas en Skype para los negocios en línea. Ahora puede habilitar sistema de teléfono en las capacidades de Office 365 y características para los usuarios alojados en Skype para los negocios en línea, pero seguirán utilizando conectividad de RTC local.
    
- Tiene una implementación local y desea mover algunos o todos los usuarios a Skype para los negocios en línea, pero seguir utilizando conectividad de RTC local.
    
    > [!IMPORTANT]
    > Para habilitar correctamente los usuarios para el sistema de teléfono en Office 365 con conectividad de RTC local, su dirección SIP debe estar en su propio dominio. No se admite el uso del dominio predeterminado para Office 365 (onmicrosoft.com). 
  
Para aprender más sobre el sistema de teléfono en Office 365, incluyendo planes y licencias, vea [llamar a PSTN planes de Skype para el negocio](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).
  
## <a name="feature-comparison"></a>Comparación de características

PBX de nube con conectividad de RTC local no ofrece la misma función de conjunto como una solución de Telefonía IP empresarial totalmente local. Para ayudarle a decidir si PBX de nube con conectividad de RTC local proporcionará la característica derecho establecido para su organización, consulte [aquí es lo que obtiene con PBX de nube](https://go.microsoft.com/fwlink/?LinkId=715517).
  
## <a name="benefits-and-planning-considerations"></a>Ventajas y consideraciones de planeamiento

> [!CAUTION]
> Los dispositivos de Lync Phone Edition TIENEN que estar actualizados con el firmware mínimo necesario en su entorno local ANTES de migrar a Skype Empresarial Online.
Si transfiere los usuarios del entorno local al entorno en línea antes de actualizar el firmware, los usuarios no se podrán conectar con sus teléfonos. Para corregir este problema, es necesario volver a transferir los usuarios al entorno local para actualizar los teléfonos con el firmware mínimo. NO INTENTE ACTUALIZAR AL FIRMWARE MÍNIMO O REALIZAR UN RESTABLECIMIENTO COMPLETO DEL TELÉFONO ANTES DE VOLVER A TRANSFERIR EL USUARIO AL ENTORNO LOCAL.
Si se realiza un restablecimiento completo cuando el dispositivo no tiene instalado el firmware mínimo, se implementará la autenticación con PIN, que no es compatible con Skype Empresarial Online. Para obtener más información, consulte [obtención de teléfonos para Skype para los negocios en línea](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).
  
Al implementar el sistema de teléfono en Office 365 con conectividad de RTC local, puede mover los usuarios a la nube a través de Skype para los negocios en línea a su propio ritmo, conservando su conectividad de RTC local. Si tiene un PBX, seguirá usándolo para proporcionar conectividad con RTC a los usuarios que transfirió a la nube. Una vez que un usuario se mueve a Skype para los negocios en línea y el sistema de teléfono en Office 365, dejarán de funcionar su teléfono PBX heredada, pero su número de teléfono enrutará a cualquiera de lo Skype para clientes de empresa para PC o teléfonos inteligentes, así como Skype para el teléfono de escritorio compatibles con el negocio s. Una vez adaptado, sistema telefónico de los usuarios de Office 365 y PBX heredadas pueden llamar mutuamente normalmente así como hacer y recibir llamadas PSTN utilizando su número de teléfono normal.
  
Puede tener una característica personalizada o un complemento principal en su PBX heredado, como un centro de llamadas. Si la función personalizada no está disponible actualmente en el sistema telefónico en Office 365, debe dejar aquellos usuarios que requieren dicha función personalizada local con PBX heredada y puerto sólo los usuarios que no necesitan tener acceso a la función personalizada al sistema de teléfono en Office 365 con conectividad de RTC local.
  
Para obtener una lista de PBX heredadas que interactúan directamente con Skype para Business Server 2015 Véase [Infraestructura calificados para Microsoft Lync](https://technet.microsoft.com/en-us/office/dn788945.aspx). Si su PBX no está en esta lista, puede utilizar un controlador de borde de sesión para conectar su PBX con el sistema de teléfono en Office 365 en Skype para los negocios en línea.
  
### <a name="network-considerations-for-quality-and-performance"></a>Consideraciones de red para calidad y rendimiento

Al implementar un servicio hospedada en la nube como sistema telefónico en Office 365 con conectividad de RTC local, debe tenga en cuenta lo siguiente. En un Skype puramente local para la implementación de Telefonía IP empresarial de Business Server 2015, la infraestructura y los clientes están en la red de la empresa. La calidad y el rendimiento de esta red, que son críticos para un audio y vídeo de alta calidad, se encuentran controlados directamente por el personal de la empresa. Con el sistema de teléfono en Office 365 con conectividad de RTC local, hay tres redes implicadas, dos de los cuales el cliente es responsable, pero sólo uno de los cuales el personal de la empresa tiene control directo sobre:
  
- **Red de distribución mundial de medios de Microsoft** Infraestructura y red global de nube de Microsoft. Office 365 y sistema de teléfono en el tráfico y los servidores de Office 365 recorren esta red.
    
- **Interconexión de Enterprise/PSTN de nube** Ésta es la red que se conecta a su empresa a la nube de Office 365. Esto no es necesariamente la misma que la conexión a Internet genérica.
    
- **La red de la empresa** La calidad de los medios de comunicación en tiempo real depende en gran medida su propia red: especialmente la red WiFi y la calidad de la interconexión utilizada para llegar a la nube de Office 365.
    
> [!NOTE]
> Para obtener más información sobre el rendimiento de optimización en Skype para los negocios en línea, vea [Ajustar Skype para el funcionamiento de los negocios en línea](https://support.office.com/en-us/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US). 
  
## <a name="prerequisites-for-using-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>Requisitos previos para usar el sistema telefónico en Office 365 con conectividad de RTC local

Para poder configurar el sistema de teléfono Office 365 con conectividad de RTC local y mover usuarios a Skype para los negocios en línea, debe confirmar que tiene los siguientes requisitos previos en su lugar:
  
 **Versiones de servidor local.** Las versiones de los servidores de la implementación local deben aparecer en la tabla siguiente para admitir el sistema telefónico en Office 365 con conectividad de RTC local.
  
|**Función de servidor**|**Versiones compatibles\***|
|:-----|:-----|
|Borde de federación\*\*  <br/> |Skype Empresarial Server 2015  <br/> |
|Servidor del grupo interno de ruta de federación del próximo salto  <br/> |Skype Empresarial Server 2015, actualización acumulativa 6.0.9319.235 de marzo de 2016 o superior (front-end o Director)  <br/> |
|Servidor de usuario front-end  <br/> |Skype Empresarial Server 2015  <br/> Lync Server 2013  <br/> |
|Servidor perimetral  <br/> |Skype Empresarial Server 2015  <br/> |
|Servidor de mediación  <br/> |Skype Empresarial Server 2015  <br/> Lync Server 2013  <br/> |
   
\*Mínimo versiones soportadas son:
  
- Skype Empresarial Server 2015, actualización acumulativa 6.0.9319.235 de marzo de 2016
    
- Lync Server 2013, actualización acumulativa 5.0.8308.920 de julio de 2015
    
\*\*La federación de ruta para todos los dominios SIP admitidos deben atravesar el Skype para ejecutar Business Server 2015 Edge Server actualización acumulativa de la marcha 2016 o superior. Si el grupo de usuarios está en Lync Server 2013, ese tráfico de grupo externo permanece en el servidor perimetral de Lync Server 2013. 
  
Además debe asegurarse de lo siguiente:
  
- **En instalaciones de Telefonía IP empresarial está configurado y probado para usuarios locales** Esto incluye los componentes de conectividad PSTN. Para obtener más información, vea los temas siguientes si utiliza Skype para Business Server 2015, vea [Implementación de Telefonía IP empresarial en Skype para Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)y [planificar para Telefonía IP empresarial en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) .
    
    Si utilizas Lync Server 2013, consulte [Diseño de Telefonía IP empresarial en Lync Server 2013](https://technet.microsoft.com/library/gg413081%28v=ocs.15%29.aspx) e [Implementación de Telefonía IP empresarial en Lync Server 2013](https://technet.microsoft.com/EN-US/library/gg412876%28v=ocs.15%29.aspx).
    
- **Sincronización de Active Directory** Debe configurar la sincronización de Active Directory con Azure Connect de AD. Para obtener más información, vea [administración de Azure Connect de AD](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect-whats-next/).
    
    > [!NOTE]
    > La versión de AAD Connect que use tiene que ser la versión 1.0.9125.0 o posterior. Si usa una versión anterior de las herramientas de AAD Connect o DirSync, actualice a la versión compatible. Puede actualizar la instalación actual y mantener las reglas personalizadas que haya definido en su entorno. 
  
- **Configurar la implementación híbrida** Si todos su Skype para usuarios de negocios están alojados ya sea en línea o locales, o si tiene actualmente una mezcla, debe completar los pasos para configurar la implementación híbrida de Skype para Business Server o Lync Server 2013, tal como se describe en [implementar híbrido conectividad entre Skype para Business Server y Skype para los negocios en línea](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md). Para obtener más información sobre implementaciones híbridas, consulte [Plan conectividad híbrida entre Skype para Business Server y Skype para los negocios en línea](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md). 
    
    Si está utilizando Lync Server 2013, consulte [Lync Server 2013 híbrido](https://technet.microsoft.com/EN-US/library/jj204805%28v=ocs.15%29.aspx).
    
- **Servicios de federación de Active Directory (AD FS) (recomendado)** Se recomienda implementar AD FS para admitir el inicio de sesión único. Para obtener más información, vea [Servicios de federación de Active Directory (AD FS)](https://technet.microsoft.com/en-us/library/cc736690%28v=ws.10%29.aspx).
    
Para obtener información acerca de la implementación de sistema de teléfono en Office 365, vea [Permitir a los usuarios para el sistema de teléfono en Office 365 con conectividad de RTC local en Skype para Business Server](enable-users-for-phone-system.md).
  

