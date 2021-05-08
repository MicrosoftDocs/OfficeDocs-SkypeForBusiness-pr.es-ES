---
title: Implementar el Skype Empresarial en Microsoft 365 ao Office 365
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8c563b81-22c9-4024-9efe-9fe28c7bbc96
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 'Obtenga información sobre cómo planear e implementar Skype Empresarial pequeñas, medianas y grandes organizaciones y hacer que esté disponible para los usuarios. '
ms.openlocfilehash: e23d4310d47bfae68a12c2b928741a2994588a57
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239903"
---
# <a name="deploy-the-skype-for-business-client-in-microsoft-365-or-office-365"></a>Implementar el Skype Empresarial en Microsoft 365 o Office 365

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

En este artículo se explican las opciones de cómo usted, el **[administrador,](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** puede implementar la aplicación Skype Empresarial a los usuarios de su organización.
  
Antes de implementar Skype Empresarial a los usuarios, asegúrese de que ha realizado los pasos 1 a 3 en el artículo [Configurar Skype Empresarial en línea.](set-up-skype-for-business-online.md) De esta forma, Skype Empresarial se configurará con su dominio, todos los usuarios tendrán sus licencias y habrá configurado la mensajería instantánea y configurar la presencia [en Skype Empresarial Online](configure-presence-in-skype-for-business-online.md) para su organización.
  
> [!NOTE]
> Para que los usuarios instalen Skype Empresarial aplicación, deben ser administradores locales en su PC o dispositivo. O bien, tendrán que formar parte de un grupo local que pueda instalar aplicaciones en su PC o dispositivos. Si los usuarios no pueden instalar software en sus dispositivos, tendrá que instalar la aplicación Skype Empresarial para ellos. 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>Para la mayoría de las pequeñas y medianas empresas

 **Instrucciones de instalación paso a paso:** Si tiene una pequeña o mediana empresa, le recomendamos que simplemente pida a los usuarios que instalen la aplicación Skype Empresarial en su EQUIPO. Apunte a estas instrucciones: [Instalar Skype Empresarial](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb). Si están usando Mac, indócalos a Configurar [Lync para Mac 2011 para Office 365](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88). La Skype Empresarial se instala por separado del resto de las Office aplicaciones.
  
 **Aplicaciones Microsoft 365 para empresas clientes:** Si su empresa usa un plan de Office 365 que incluye Aplicaciones Microsoft 365 para empresas, como el plan E3, la aplicación Skype Empresarial se instala al mismo tiempo que los usuarios descargan e instalan Word, Excel, PowerPoint, etc. Esto también significa que no pueden desinstalar Skype Empresarial a menos que desinstale todas las Office.
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>Elegir si desea que Skype Empresarial disponible para los usuarios

Como [administrador,](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) puede elegir si quiere que la aplicación Skype Empresarial esté disponible para los usuarios.
  
- Para controlar si todos los usuarios de su empresa obtienen el **software:** inicie sesión en el centro de administración de Microsoft 365, vaya a Instalar mi **software** y, a continuación, seleccione el software que desea que esté disponible para los usuarios.
    
    ![Elija el software que desea que esté disponible para los usuarios de su empresa.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- Para controlar si determinadas personas de su empresa obtienen el **software:** inicie sesión en el Centro de administración de Microsoft 365, vaya a Usuarios usuarios activos, seleccione la persona a la que desea dar acceso al software y, a continuación, haga clic en Editar junto a Licencias de producto y active o desactive la  >  licencia.  
    
    ![Elija el software al que desea que acceda el usuario.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> Si necesita ver qué planes están asignados a personas de su organización, inicie sesión en el centro de administración de Microsoft 365 de > **Usuarios**  >  **activos.** Seleccione la persona de la lista y, a continuación, busque en **Licencias de producto.** Si usa el centro de administración clásico, busque en **Licencia asignada.** 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>Implementación manual de Skype Empresarial a los usuarios
<a name="bkmk_manual_1"> </a>

Si desea que los usuarios instalen la aplicación Skype Empresarial desde una ubicación de la red en lugar de desde Internet, puede descargar los archivos de instalación. Para ello, vaya a la **sección Implementar manualmente software** de usuario del centro de Microsoft 365 de administración. A continuación, puede **seleccionar Instalar** y guardar la configuración .exe archivo en una ubicación de red.
  
Otra opción es descargar la aplicación Skype Empresarial Basic para los usuarios. Puede descargar [Microsoft Skype Empresarial Basic (32 o 64 bits).](https://www.microsoft.com/download/details.aspx?id=49440)
  
Para las aplicaciones de Skype Empresarial completa y básica, después de descargar los archivos de configuración, tendrá que enviar manualmente (por ejemplo, por correo electrónico) la ruta de red a los usuarios para que puedan ejecutar el programa de instalación para instalar la aplicación en su equipo.
  
También puede usar estas descargas para implementar la aplicación Skype Empresarial a los usuarios mediante las herramientas y procesos de implementación de software existentes.
  
## <a name="for-larger-and-enterprise-organizations"></a>Para organizaciones grandes y empresariales

> [!NOTE]
> Esta sección solo se aplica a la aplicación Skype Empresarial disponible a través de Office 365 planes. Si su organización usa una versión con licencia por volumen de la aplicación Skype Empresarial Windows, que está basada en instalador (MSI), vea Personalizar la instalación de cliente Windows en [Skype Empresarial Server](../../SfbServer/deploy/deploy-clients/customize-windows-client-installation.md).
  
En muchas empresas u organizaciones grandes, los usuarios no pueden instalar software en sus equipos. En su lugar, los departamentos de TI implementan el software necesario en los equipos de los usuarios. Es posible que los departamentos de TI también quieran controlar la cantidad de ancho de banda de red o Internet que se usa en su organización, por lo que quieren instalar software desde una ubicación cercana en su red en lugar de hacerlo a través de Internet o en toda la red corporativa.
  
Con Office 365, tiene varias opciones para implementar la aplicación Skype Empresarial si desea controlar desde dónde está instalada. Algunas de estas opciones son las siguientes:
  
- Descargue la Skype Empresarial a su red local desde el centro de administración de Microsoft 365, tal y como se describe en Implementar manualmente Skype Empresarial [a los usuarios.](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)
    
- Use la **[Office de implementación para](https://go.microsoft.com/fwlink/p/?LinkID=626065)** descargar Aplicaciones Microsoft 365 para empresas o la aplicación Skype Empresarial a la red local. A continuación, use la Office de implementación para implementar la aplicación a los usuarios. La Office de implementación de Office le permite controlar determinados aspectos de la implementación, como los idiomas y la versión (32 bits o 64 bits).
    
- Use las herramientas y procesos de implementación de software existentes, como Microsoft Endpoint Configuration Manager, para implementar Aplicaciones Microsoft 365 para empresas o la aplicación Skype Empresarial a los usuarios. Puede usar las herramientas y procesos existentes con la herramienta de implementación [Office](https://go.microsoft.com/fwlink/p/?LinkID=626065) o con el software que ha descargado desde el centro de administración Microsoft 365 usuario.
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>Más información sobre el uso de la Office de implementación

Para obtener más información sobre cómo descargar la Herramienta de implementación de Office y más información sobre cómo instalar la aplicación Skype Empresarial y otras aplicaciones cliente Office 365, vea Administrar la configuración de descarga de [software en Office 365](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360).
  
A continuación se ofrece información general sobre los pasos necesarios para usar la herramienta de Office implementación para implementar una aplicación:
  
1. **[Descargue la herramienta de Office de implementación más](https://www.microsoft.com/download/details.aspx?id=49117)** reciente desde el Centro de descarga de Microsoft.
    
2. Cree el archivo configuration.xml que se usará con la Herramienta de implementación de Office que tiene la configuración de la aplicación cliente que desea, como configurar la versión (32 bits o 64 bits), el idioma de instalación, etc.
    
3. Use la Office de implementación y el archivo configuration.xml para descargar los archivos de instalación a su red local o interna desde el Office Content Delivery Network (CDN).
    
4. Use Office de implementación y el configuration.xml para instalar las aplicaciones Office cliente, incluida Skype Empresarial aplicación.
    
Para obtener más información sobre el Office de implementación y el configuration.xml, vea los siguientes artículos:
  
- [Office Información general sobre la Herramienta de implementación](/deployoffice/overview-office-deployment-tool)
    
- [Configuration.xml configuración](/deployoffice/office-deployment-tool-configuration-options)
    
### <a name="more-info-on-using-microsoft-endpoint-configuration-manager"></a>Más información sobre cómo usar Microsoft Endpoint Configuration Manager

Puede usar las herramientas y procesos de implementación de software existentes, como Microsoft Endpoint Configuration Manager, para implementar la aplicación Skype Empresarial software. Puede usar estas herramientas y procesos con el software que descargue desde el centro de administración de Microsoft 365 o con la herramienta Office implementación.
  
Para obtener más información sobre cómo usar Configuration Manager para implementar software, vea los siguientes artículos:
  
- [Crear aplicaciones en Configuration Manager](/configmgr/apps/deploy-use/create-applications)
    
- [Implementar aplicaciones con Configuration Manager](/configmgr/apps/deploy-use/deploy-applications)
    
Si va a implementar la aplicación Skype Empresarial como parte de la implementación de Aplicaciones Microsoft 365 para empresas, vea Administrar Aplicaciones Microsoft 365 para empresas [con Configuration Manager](/configmgr/sum/deploy-use/manage-office-365-proplus-updates).
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>Planeación de actualizaciones en la Skype Empresarial aplicación

Como parte de la implementación de Skype Empresarial aplicación, debe tener en cuenta cómo desea obtener actualizaciones después de Skype Empresarial está instalado. Estas actualizaciones pueden incluir nuevas características, actualizaciones de seguridad o actualizaciones que no son de seguridad, como actualizaciones que proporcionan mejoras de rendimiento o estabilidad. Las dos cosas principales que debe tener en cuenta son:
  
- ¿De dónde quiere obtener actualizaciones?
    
- ¿Con qué frecuencia desea obtener actualizaciones de características?
    
Aunque puede controlar de dónde obtiene las actualizaciones y la frecuencia con la que recibe actualizaciones de características, no puede elegir qué actualizaciones de seguridad específicas o actualizaciones que no son de seguridad que obtiene.
  
 **Dónde obtener actualizaciones desde**
  
De forma predeterminada, una vez Skype Empresarial la aplicación, las actualizaciones se descargarán automáticamente de Internet cuando estén disponibles desde Microsoft. Si desea tener más control sobre cuándo se producen las actualizaciones o desde dónde se instalan las actualizaciones, puede usar la herramienta de implementación Office o la directiva de grupo para configurarlo.
  
Por ejemplo, muchas organizaciones quieren probar actualizaciones con un grupo de usuarios antes de implementarlas en toda la organización. Para ello, use la herramienta de implementación de Office o la directiva de grupo para configurar la aplicación Skype Empresarial para obtener actualizaciones desde una ubicación específica de la red, en lugar de hacerlo automáticamente desde Internet. A continuación, puede usar la Office implementación local para descargar las actualizaciones cada mes en su red local.
  
Para obtener más información sobre cómo funcionan las actualizaciones Office 365 software, vea estos artículos:
  
- [Información general sobre el proceso de actualización para Aplicaciones Microsoft 365 para empresas](/deployoffice/overview-update-process-microsoft-365-apps)
    
- [Elija cómo administrar actualizaciones para Aplicaciones Microsoft 365 para empresas](/deployoffice/choose-how-manage-updates-microsoft-365-apps)
    
- [Configurar la configuración de actualización para Aplicaciones Microsoft 365 para empresas](/deployoffice/configure-update-settings-microsoft-365-apps)
    
  **Con qué frecuencia se obtienen actualizaciones de características**
  
Además de dónde obtiene actualizaciones, también puede controlar la frecuencia con la que obtiene nuevas características para el Skype Empresarial cliente. Las dos opciones son las siguientes:
  
- Obtener actualizaciones de características cada mes, si hay nuevas características
    
- Obtener actualizaciones de características cada seis meses
    
Para algunas organizaciones, quieren tener tiempo para probar nuevas características, por lo que solo quieren recibir actualizaciones de características dos veces al año en lugar de cada mes.
  
Puede controlar la frecuencia con la que recibe actualizaciones de características mediante la herramienta de Office de implementación o la directiva de grupo para configurar el canal de actualización. El Canal mensual le proporciona actualizaciones de características mensuales (aproximadamente), mientras que el canal de Semi-Annual le proporciona actualizaciones de características cada seis meses. Para obtener más información sobre los canales, vea [Información general sobre los canales de](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)actualización para Aplicaciones Microsoft 365 para empresas .
  
## <a name="related-topics"></a>Temas relacionados

[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)
  
[Licencias complementarias de Skype Empresarial y Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
