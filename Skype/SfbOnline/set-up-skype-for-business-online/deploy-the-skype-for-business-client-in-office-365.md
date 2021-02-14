---
title: Implementar el cliente de Skype Empresarial en Microsoft 365 o en Office 365
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
description: 'Aprenda a planificar e implementar Skype Empresarial en organizaciones pequeñas, medianas y grandes, y a hacer que esté disponible para sus usuarios. '
ms.openlocfilehash: d7c310935c5fa97873183d18b264616404471895
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777245"
---
# <a name="deploy-the-skype-for-business-client-in-microsoft-365-or-office-365"></a>Implementar el cliente de Skype Empresarial en Microsoft 365 u Office 365

En este artículo se explican las opciones sobre cómo el **[administrador](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** puede implementar la aplicación Skype Empresarial a los usuarios de su organización.
  
Antes de implementar Skype Empresarial a los usuarios, asegúrese de que ha realizado los pasos 1 a 3 del artículo Configurar [Skype Empresarial Online.](set-up-skype-for-business-online.md) De esta forma, Skype Empresarial se configurará con su dominio, todos los usuarios tendrán sus licencias y habrá configurado la mensajería instantánea y configurar la presencia en Skype Empresarial [Online](configure-presence-in-skype-for-business-online.md) para su organización.
  
> [!NOTE]
> Para que los usuarios puedan instalar la aplicación Skype Empresarial, deben ser administradores locales en su equipo o dispositivo. O bien, tendrán que formar parte de un grupo local que pueda instalar aplicaciones en su EQUIPO o dispositivos. Si los usuarios no tienen permiso para instalar software en sus dispositivos, tendrá que instalar la aplicación Skype Empresarial para ellos. 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>Para la mayoría de las empresas medianas y pequeñas

 **Instrucciones de instalación paso a paso:** Si tiene una empresa pequeña o mediana, le recomendamos que simplemente pida a los usuarios que instalen la aplicación Skype Empresarial en su EQUIPO. Resalte sobre estas instrucciones: [Instalar Skype Empresarial.](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb) Si usan equipos Mac, indicóles que [configuren Lync para Mac 2011 para Office 365.](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88) La aplicación de Skype Empresarial se instala por separado del resto de las aplicaciones de Office.
  
 **Aplicaciones de Microsoft 365 para clientes empresariales:** Si su empresa usa un plan de Office 365 que incluye las aplicaciones de Microsoft 365 para empresas, como el plan E3, la aplicación Skype Empresarial se instala al mismo tiempo que los usuarios descargan e instalan Word, Excel, PowerPoint, etc. Esto también significa que no pueden desinstalar Skype Empresarial a menos que desinstale toda Office.
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>Elegir si Skype Empresarial está disponible para los usuarios

Como [administrador,](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) puede elegir si quiere que la aplicación de Skype Empresarial esté disponible para los usuarios.
  
- Para controlar si todos los usuarios de su empresa obtienen el **software:** inicie sesión en el Centro de administración de Microsoft 365, vaya a Instalar mi **software** y, a continuación, seleccione el software que desea que esté disponible para los usuarios.
    
    ![Elija el software que quiere que esté disponible para los usuarios de su empresa.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- Para controlar si determinados usuarios de su empresa obtienen el **software:** inicie sesión en el Centro de administración de Microsoft 365, vaya a Usuarios activos, seleccione la persona a la que desea dar acceso al software y, a continuación, haga clic en Editar junto a licencias de producto y active o desactive la  >  licencia.  
    
    ![Elija el software al que desea que acceda el usuario.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> Si necesita ver qué planes están asignados a los usuarios de su organización, inicie sesión en el Centro de administración de Microsoft 365 > **Usuarios**  >  **activos.** Seleccione la persona de la lista y busque en **Licencias de producto.** Si usa el Centro de administración clásico, busque en **Licencia asignada.** 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>Implementar de forma manual Skype Empresarial para los usuarios
<a name="bkmk_manual_1"> </a>

Si desea que los usuarios instalen la aplicación Skype Empresarial desde una ubicación en la red en lugar de desde Internet, puede descargar los archivos de instalación. Para ello, vaya a la sección Software de usuario de implementación **manual** del Centro de administración de Microsoft 365. A continuación, puede **seleccionar Instalar** y guardar el archivo .exe de configuración en una ubicación de red.
  
Otra opción es descargar la aplicación Skype Empresarial Basic para sus usuarios. Puede descargar [Microsoft Skype Empresarial Basic (32 o 64 bits).](https://www.microsoft.com/download/details.aspx?id=49440)
  
Para las aplicaciones de Skype Empresarial completa y básica, después de descargar los archivos de configuración, tendrá que enviar manualmente (por ejemplo, en un correo electrónico) la ruta de red a los usuarios para que puedan ejecutar el programa de instalación para instalar la aplicación en su equipo.
  
También puede usar estas descargas para implementar la aplicación Skype Empresarial a los usuarios mediante el uso de sus procesos y herramientas de implementación de software existentes.
  
## <a name="for-larger-and-enterprise-organizations"></a>Para organizaciones grandes y empresariales

> [!NOTE]
> Esta sección solo se aplica a la aplicación Skype Empresarial disponible a través de los planes de Office 365. Si su organización usa una versión con licencia por volumen de la aplicación Skype Empresarial, que está basada en Windows Installer (MSI), consulte Personalizar la instalación de cliente de [Windows en Skype Empresarial Server.](https://technet.microsoft.com/library/jj204934.aspx)
  
En muchas empresas o grandes organizaciones, los usuarios no tienen permiso para instalar software en sus equipos. En su lugar, los departamentos de TI implementan el software necesario en los equipos de los usuarios. Es posible que los departamentos de TI también quieran controlar la cantidad de ancho de banda de red o de Internet que se usa en su organización, por lo que quieren instalar software desde una ubicación próxima en su red, en lugar de hacerlo a través de Internet o de una red corporativa.
  
Con Office 365, tiene varias opciones para implementar la aplicación de Skype Empresarial si quiere controlar desde dónde se instala. Algunas de estas opciones son las siguientes:
  
- Descargue la aplicación Skype Empresarial en su red local desde el Centro de administración de Microsoft 365, como se describe en Implementar manualmente Skype Empresarial [a los usuarios.](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)
    
- Use la **[Herramienta de implementación de Office](https://go.microsoft.com/fwlink/p/?LinkID=626065)** para descargar las aplicaciones de Microsoft 365 para empresas o la aplicación de Skype Empresarial en su red local. Después, use la Herramienta de implementación de Office para implementar la aplicación a los usuarios. La Herramienta de implementación de Office le permite controlar ciertos aspectos de la implementación, como los idiomas y la versión (32 bits o 64 bits).
    
- Use sus procesos y herramientas de implementación de software existentes, como Microsoft Endpoint Configuration Manager, para implementar las aplicaciones de Microsoft 365 para empresas o la aplicación skype empresarial a los usuarios. Puede usar sus procesos y herramientas existentes con la Herramienta de implementación de [Office](https://go.microsoft.com/fwlink/p/?LinkID=626065) o con el software que ha descargado desde el Centro de administración de Microsoft 365.
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>Más información sobre el uso de la Herramienta de implementación de Office

Para obtener más información sobre cómo descargar la Herramienta de implementación de Office y sobre cómo instalar la aplicación de Skype Empresarial y otras aplicaciones cliente de Office 365, vea Administrar la configuración de descarga de [software en Office 365.](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360)
  
Aquí tiene información general sobre los pasos necesarios para usar la Herramienta de implementación de Office para implementar una aplicación:
  
1. **[Descargue la herramienta de implementación de Office más reciente](https://www.microsoft.com/download/details.aspx?id=49117)** desde el Centro de descarga de Microsoft.
    
2. Cree el archivo configuration.xml que se usará con la Herramienta de implementación de Office que tenga la configuración de la aplicación cliente que desee, como establecer la versión (32 bits o 64 bits), el idioma de instalación, etc.
    
3. Use la Herramienta de implementación de Office y el archivo configuration.xml para descargar los archivos de configuración en su red local o interna desde la red de entrega de contenido (CDN) de Office.
    
4. Use la Herramienta de implementación de Office configuration.xml instalar las aplicaciones cliente de Office, incluida la aplicación de Skype Empresarial.
    
Para obtener más información sobre cómo usar la Herramienta de implementación de Office configuration.xml un archivo, vea los artículos siguientes:
  
- [Información general de la Herramienta de implementación de Office](https://technet.microsoft.com/library/jj219422.aspx)
    
- [Configuration.xml configuración](https://technet.microsoft.com/library/jj219426.aspx)
    
### <a name="more-info-on-using-microsoft-endpoint-configuration-manager"></a>Más información sobre el uso de Microsoft Endpoint Configuration Manager

Puede usar sus procesos y herramientas de implementación de software existentes, como Microsoft Endpoint Configuration Manager, para implementar la aplicación de Skype Empresarial. Puede usar estas herramientas y procesos con el software que descargó desde el Centro de administración de Microsoft 365 o con la Herramienta de implementación de Office.
  
Para obtener más información sobre cómo usar Configuration Manager para implementar software, vea los artículos siguientes:
  
- [Crear aplicaciones en Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/create-applications)
    
- [Implementar aplicaciones con Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
    
Si va a implementar la aplicación Skype Empresarial como parte de la implementación de las aplicaciones de Microsoft 365 para empresas, vea Administrar las aplicaciones de [Microsoft 365](https://docs.microsoft.com/configmgr/sum/deploy-use/manage-office-365-proplus-updates)para empresas con Configuration Manager.
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>Planificación de las actualizaciones de la aplicación de Skype Empresarial

Como parte de la implementación de la aplicación skype empresarial, debe tener en cuenta cómo quiere obtener actualizaciones después de instalar Skype Empresarial. Estas actualizaciones pueden incluir nuevas características, actualizaciones de seguridad o actualizaciones no de seguridad, como actualizaciones que ofrecen mejoras de rendimiento o estabilidad. Los dos aspectos principales que debe tener en cuenta son:
  
- ¿Desde dónde quiere obtener las actualizaciones?
    
- Frecuencia con la que desea obtener actualizaciones de características
    
Aunque puede controlar desde dónde se descargarán las actualizaciones y la frecuencia con la que se descargarán las actualizaciones de características, no puede elegir las actualizaciones de seguridad específicas o las actualizaciones no de seguridad que se obtienen.
  
 **Desde dónde obtener actualizaciones**
  
De forma predeterminada, después de instalar la aplicación de Skype Empresarial, las actualizaciones se descargarán automáticamente de Internet cuando estén disponibles desde Microsoft. Si quiere tener más control sobre cuándo se producen las actualizaciones o desde dónde se instalan, puede usar la Herramienta de implementación de Office o una directiva de grupo para configurarlo.
  
Por ejemplo, muchas organizaciones quieren probar actualizaciones con un grupo de usuarios antes de implementarlas en toda la organización. Para hacerlo, puede usar la Herramienta de implementación de Office o una directiva de grupo para configurar la aplicación de Skype Empresarial y obtener actualizaciones desde una ubicación específica de su red, en lugar de hacerlo automáticamente desde Internet. Después, puede usar la Herramienta de implementación de Office para descargar las actualizaciones cada mes en su red local.
  
Para obtener más información sobre cómo funcionan las actualizaciones para el software de Office 365, vea estos artículos:
  
- [Información general sobre el proceso de actualización de las aplicaciones de Microsoft 365 para empresas](https://technet.microsoft.com/library/dn761709.aspx)
    
- [Elegir cómo administrar las actualizaciones de las aplicaciones de Microsoft 365 para empresas](https://technet.microsoft.com/library/dn761707.aspx)
    
- [Configurar las opciones de actualización de las aplicaciones de Microsoft 365 para empresas](https://technet.microsoft.com/library/dn761708.aspx)
    
  **Frecuencia con que se obtienen actualizaciones de características**
  
Además de desde dónde se descargarán las actualizaciones, también puede controlar la frecuencia con la que recibe nuevas características para el cliente de Skype Empresarial. Las dos opciones son las siguientes:
  
- Obtener actualizaciones de características cada mes, si hay nuevas características
    
- Obtener actualizaciones de características cada seis meses
    
En algunas organizaciones, quieren tener tiempo para probar nuevas características, por lo que solo quieren obtener actualizaciones de características dos veces al año, en lugar de cada mes.
  
Puede controlar la frecuencia con la que recibe actualizaciones de características con la Herramienta de implementación de Office o una directiva de grupo para configurar el canal de actualización. El Canal mensual le ofrece actualizaciones de características mensualmente (aproximadamente), mientras que el Semi-Annual mensual le ofrece actualizaciones de características cada seis meses. Para obtener más información sobre los canales, vea Información general sobre los canales de actualización de las aplicaciones de [Microsoft 365 para empresas.](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)
  
## <a name="related-topics"></a>Temas relacionados

[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)
  
[Licencias complementarias de Skype Empresarial y Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
