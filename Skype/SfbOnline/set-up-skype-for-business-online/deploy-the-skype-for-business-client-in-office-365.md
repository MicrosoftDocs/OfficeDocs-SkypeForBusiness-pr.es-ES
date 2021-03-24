---
title: Implementar el cliente de Skype Empresarial en Microsoft 365 o Office 365
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
description: 'Obtenga información sobre cómo planear e implementar Skype Empresarial en pequeñas, medianas y grandes organizaciones y hacer que esté disponible para los usuarios. '
ms.openlocfilehash: 7a2ba51a315b77c501735be863f342c1bdb1548f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097296"
---
# <a name="deploy-the-skype-for-business-client-in-microsoft-365-or-office-365"></a>Implementar el cliente de Skype Empresarial en Microsoft 365 u Office 365

En este artículo se explican las opciones de cómo usted, el **[administrador,](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** puede implementar la aplicación de Skype Empresarial a los usuarios de su organización.
  
Antes de implementar Skype Empresarial para los usuarios, asegúrese de que ha realizado los pasos 1 a 3 en el artículo Configurar [Skype Empresarial Online.](set-up-skype-for-business-online.md) De esta forma, Skype Empresarial se configurará con su dominio, todos los usuarios tendrán sus licencias y habrá configurado la mensajería instantánea y configurar la presencia en [Skype Empresarial Online](configure-presence-in-skype-for-business-online.md) para su organización.
  
> [!NOTE]
> Para que los usuarios instalen la aplicación de Skype Empresarial, deben ser administradores locales en su PC o dispositivo. O bien, tendrán que formar parte de un grupo local que pueda instalar aplicaciones en su PC o dispositivos. Si los usuarios no pueden instalar software en sus dispositivos, tendrá que instalar la aplicación de Skype Empresarial para ellos. 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>Para la mayoría de las pequeñas y medianas empresas

 **Instrucciones de instalación paso a paso:** Si tiene una pequeña o mediana empresa, le recomendamos que simplemente pida a los usuarios que instalen la aplicación de Skype Empresarial en su PC. Apunte a estas instrucciones: [Instalar Skype Empresarial.](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb) Si están usando Mac, indócalos a Configurar [Lync para Mac 2011 para Office 365.](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88) La aplicación de Skype Empresarial se instala por separado del resto de las aplicaciones de Office.
  
 **Aplicaciones de Microsoft 365 para clientes empresariales:** Si su empresa usa un plan de Office 365 que incluye aplicaciones de Microsoft 365 para empresas, como el plan E3, la aplicación Skype Empresarial se instala al mismo tiempo que los usuarios descargan e instalan Word, Excel, PowerPoint, etc. Esto también significa que no pueden desinstalar Skype Empresarial a menos que desinstale toda Office.
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>Elegir si quiere que Skype Empresarial esté disponible para los usuarios

Como [administrador,](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) puede elegir si quiere que la aplicación de Skype Empresarial esté disponible para los usuarios.
  
- Para controlar si todos los usuarios de su empresa obtienen el **software:** inicie sesión en el Centro de administración de Microsoft 365, vaya a Instalar mi **software** y, a continuación, seleccione el software que desea que esté disponible para los usuarios.
    
    ![Elija el software que desea que esté disponible para los usuarios de su empresa.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- Para controlar si determinadas personas de su empresa obtienen el **software:** inicie sesión en el Centro de administración de Microsoft 365, vaya a Usuarios usuarios activos, seleccione la persona a la que desea dar acceso al software y, a continuación, haga clic en Editar junto a Licencias de producto y active o desactive la  >  licencia.  
    
    ![Elija el software al que desea que acceda el usuario.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> Si necesita ver qué planes se asignan a personas de su organización, inicie sesión en el Centro de administración de Microsoft 365 > **Usuarios**  >  **activos.** Seleccione la persona de la lista y, a continuación, busque en **Licencias de producto.** Si usa el centro de administración clásico, busque en **Licencia asignada.** 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>Implementación manual de Skype Empresarial para los usuarios
<a name="bkmk_manual_1"> </a>

Si quiere que los usuarios instalen la aplicación de Skype Empresarial desde una ubicación de su red en lugar de desde Internet, puede descargar los archivos de configuración. Para ello, vaya a la **sección Implementar manualmente software** de usuario del Centro de administración de Microsoft 365. A continuación, puede **seleccionar Instalar** y guardar el archivo .exe de configuración en una ubicación de red.
  
Otra opción es descargar la aplicación Skype Empresarial Basic para los usuarios. Puede descargar [Microsoft Skype Empresarial Basic (32 o 64 bits).](https://www.microsoft.com/download/details.aspx?id=49440)
  
Para las aplicaciones de Skype Empresarial completa y básica, después de descargar los archivos de configuración, tendrá que enviar manualmente (por ejemplo, por correo electrónico) la ruta de red a los usuarios para que puedan ejecutar el programa de instalación para instalar la aplicación en su equipo.
  
También puede usar estas descargas para implementar la aplicación de Skype Empresarial a los usuarios mediante sus procesos y herramientas de implementación de software existentes.
  
## <a name="for-larger-and-enterprise-organizations"></a>Para organizaciones grandes y empresariales

> [!NOTE]
> Esta sección solo se aplica a la aplicación de Skype Empresarial disponible a través de los planes de Office 365. Si su organización usa una versión con licencia por volumen de la aplicación Skype Empresarial, que está basada en Windows Installer (MSI), vea Personalizar la instalación del cliente [de Windows en Skype Empresarial Server.](../../SfbServer/deploy/deploy-clients/customize-windows-client-installation.md)
  
En muchas empresas u organizaciones grandes, los usuarios no pueden instalar software en sus equipos. En su lugar, los departamentos de TI implementan el software necesario en los equipos de los usuarios. Es posible que los departamentos de TI también quieran controlar la cantidad de ancho de banda de red o Internet que se usa en su organización, por lo que quieren instalar software desde una ubicación cercana en su red en lugar de hacerlo a través de Internet o en toda la red corporativa.
  
Con Office 365, tiene varias opciones para implementar la aplicación de Skype Empresarial si quiere controlar desde dónde está instalada. Algunas de estas opciones son las siguientes:
  
- Descargue la aplicación de Skype Empresarial en su red local desde el Centro de administración de Microsoft 365, tal y como se describe en Implementación manual de Skype Empresarial [para los usuarios.](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)
    
- Use la **[Herramienta de implementación de Office](https://go.microsoft.com/fwlink/p/?LinkID=626065)** para descargar aplicaciones de Microsoft 365 para empresas o la aplicación de Skype Empresarial a su red local. A continuación, use la Herramienta de implementación de Office para implementar la aplicación a los usuarios. La Herramienta de implementación de Office le ofrece la capacidad de controlar determinados aspectos de la implementación, como los idiomas y la versión (32 bits o 64 bits).
    
- Use sus procesos y herramientas de implementación de software existentes, como Microsoft Endpoint Configuration Manager, para implementar aplicaciones de Microsoft 365 para empresas o la aplicación skype empresarial para los usuarios. Puede usar las herramientas y procesos existentes con la Herramienta de implementación de [Office](https://go.microsoft.com/fwlink/p/?LinkID=626065) o con el software que descargó desde el Centro de administración de Microsoft 365.
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>Más información sobre el uso de la Herramienta de implementación de Office

Para obtener más información sobre cómo descargar la Herramienta de implementación de Office y más información sobre cómo instalar la aplicación de Skype Empresarial y otras aplicaciones cliente de Office 365, vea Administrar la configuración de descarga de software en [Office 365.](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360)
  
A continuación se ofrece información general sobre los pasos necesarios para usar la Herramienta de implementación de Office para implementar una aplicación:
  
1. **[Descargue la herramienta de implementación más reciente de Office](https://www.microsoft.com/download/details.aspx?id=49117)** desde el Centro de descarga de Microsoft.
    
2. Cree el archivo configuration.xml que se usará con la Herramienta de implementación de Office que tiene la configuración de la aplicación cliente que desea, como configurar la versión (32 bits o 64 bits), el idioma de instalación, etc.
    
3. Use la Herramienta de implementación de Office y el archivo configuration.xml para descargar los archivos de configuración en su red local o interna desde la Red de entrega de contenido (CDN) de Office.
    
4. Use la Herramienta de implementación de Office y configuration.xml para instalar las aplicaciones cliente de Office, incluida la aplicación de Skype Empresarial.
    
Para obtener más información sobre cómo usar la Herramienta de implementación de Office y configuration.xml, vea los siguientes artículos:
  
- [Información general sobre la Herramienta de implementación de Office](/deployoffice/overview-office-deployment-tool)
    
- [Configuration.xml configuración](/deployoffice/office-deployment-tool-configuration-options)
    
### <a name="more-info-on-using-microsoft-endpoint-configuration-manager"></a>Más información sobre cómo usar Microsoft Endpoint Configuration Manager

Puede usar sus procesos y herramientas de implementación de software existentes, como Microsoft Endpoint Configuration Manager, para implementar la aplicación de Skype Empresarial. Puede usar estas herramientas y procesos con el software que descargue desde el Centro de administración de Microsoft 365 o con la Herramienta de implementación de Office.
  
Para obtener más información sobre cómo usar Configuration Manager para implementar software, vea los siguientes artículos:
  
- [Crear aplicaciones en Configuration Manager](/configmgr/apps/deploy-use/create-applications)
    
- [Implementar aplicaciones con Configuration Manager](/configmgr/apps/deploy-use/deploy-applications)
    
Si va a implementar la aplicación de Skype Empresarial como parte de la implementación de aplicaciones de Microsoft 365 para empresas, vea Administrar aplicaciones de [Microsoft 365](/configmgr/sum/deploy-use/manage-office-365-proplus-updates)para empresas con Configuration Manager.
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>Planeación de actualizaciones en la aplicación Skype Empresarial

Como parte de la implementación de la aplicación Skype Empresarial, debe considerar cómo desea obtener actualizaciones después de instalar Skype Empresarial. Estas actualizaciones pueden incluir nuevas características, actualizaciones de seguridad o actualizaciones que no son de seguridad, como actualizaciones que proporcionan mejoras de rendimiento o estabilidad. Las dos cosas principales que debe tener en cuenta son:
  
- ¿De dónde quiere obtener actualizaciones?
    
- ¿Con qué frecuencia desea obtener actualizaciones de características?
    
Aunque puede controlar de dónde obtiene las actualizaciones y la frecuencia con la que recibe actualizaciones de características, no puede elegir qué actualizaciones de seguridad específicas o actualizaciones que no son de seguridad que obtiene.
  
 **Dónde obtener actualizaciones desde**
  
De forma predeterminada, después de instalar la aplicación Skype Empresarial, las actualizaciones se descargarán automáticamente de Internet cuando estén disponibles desde Microsoft. Si desea tener más control sobre cuándo se producen las actualizaciones o desde dónde están instaladas, puede usar la Herramienta de implementación de Office o la directiva de grupo para configurarlo.
  
Por ejemplo, muchas organizaciones quieren probar actualizaciones con un grupo de usuarios antes de implementarlas en toda la organización. Para ello, use la Herramienta de implementación de Office o la directiva de grupo para configurar la aplicación de Skype Empresarial para obtener actualizaciones desde una ubicación específica de su red, en lugar de hacerlo automáticamente desde Internet. A continuación, puede usar la Herramienta de implementación de Office para descargar las actualizaciones cada mes en su red local.
  
Para obtener más información sobre cómo funcionan las actualizaciones para el software de Office 365, vea estos artículos:
  
- [Información general sobre el proceso de actualización de aplicaciones de Microsoft 365 para empresas](/deployoffice/overview-update-process-microsoft-365-apps)
    
- [Elegir cómo administrar actualizaciones de Aplicaciones de Microsoft 365 para empresas](/deployoffice/choose-how-manage-updates-microsoft-365-apps)
    
- [Configurar la configuración de actualización de las aplicaciones de Microsoft 365 para empresas](/deployoffice/configure-update-settings-microsoft-365-apps)
    
  **Con qué frecuencia se obtienen actualizaciones de características**
  
Además de dónde recibe las actualizaciones, también puede controlar la frecuencia con la que obtiene nuevas características para el cliente de Skype Empresarial. Las dos opciones son las siguientes:
  
- Obtener actualizaciones de características cada mes, si hay nuevas características
    
- Obtener actualizaciones de características cada seis meses
    
Para algunas organizaciones, quieren tener tiempo para probar nuevas características, por lo que solo quieren recibir actualizaciones de características dos veces al año en lugar de cada mes.
  
Puede controlar la frecuencia con la que recibe actualizaciones de características mediante la Herramienta de implementación de Office o la directiva de grupo para configurar el canal de actualización. El Canal mensual le proporciona actualizaciones de características mensuales (aproximadamente), mientras que el canal de Semi-Annual le proporciona actualizaciones de características cada seis meses. Para obtener más información sobre los canales, vea Información general sobre los canales de actualización [para aplicaciones de Microsoft 365 para empresas.](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)
  
## <a name="related-topics"></a>Temas relacionados

[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)
  
[Licencias complementarias de Skype Empresarial y Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
