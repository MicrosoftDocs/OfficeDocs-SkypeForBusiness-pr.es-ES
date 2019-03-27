---
title: Implementar el Skype para cliente empresarial en Office 365
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 'Obtenga información sobre cómo planear e implementar Skype para la empresa en organizaciones pequeñas, medianas y grandes y ponerlo a disposición de los usuarios. '
ms.openlocfilehash: 6dccd022d82519c1dfdce13f767e5b0a2531eb10
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896797"
---
# <a name="deploy-the-skype-for-business-client-in-office-365"></a>Implementar el Skype para cliente empresarial en Office 365

En este artículo se explica las opciones para cómo, la **[administración](https://support.office.com/en-us/article/eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US)**, puede implementar la Skype para la aplicación empresarial a las personas de su organización.
  
Antes de implementar Skype para empresarial a los usuarios, asegúrese de que ha realizado los pasos 1-3 en el artículo [Configurar Skype para profesionales en línea](set-up-skype-for-business-online.md). De este modo, Skype para la empresa se configurará con su dominio, todos los usuarios tendrán sus licencias y habrá configurado mensajería instantánea y [presencia de Configure en Skype para empresarial en línea](configure-presence-in-skype-for-business-online.md) para su organización.
  
> [!NOTE]
> Para que los usuarios instalen el Skype para la aplicación empresarial, deben ser administradores locales en su PC o dispositivo. O bien, deben formar parte de un grupo local que puede instalar aplicaciones en su PC o dispositivos. Si los usuarios no tienen permiso para instalar software en sus dispositivos, debe instalar el Skype para la aplicación empresarial para ellos. 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>Para la mayoría de las empresas pequeña y medianas

 **Instrucciones de instalación paso a paso:** Si tiene una pequeña o mediana empresa, se recomienda pedir simplemente a los usuarios que instalen el Skype para la aplicación empresarial de su PC. Apunten a estas instrucciones: [Instalar Skype para la empresa](https://support.office.com/en-us/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb?ui=en-US&rs=en-US&ad=US). Si están usando Mac, elija Configurar [Lync para Mac 2011 para Office 365](https://support.office.com/en-us/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88?ui=en-US&rs=en-US&ad=US). El Skype para la aplicación empresarial se instala por separado desde el resto de las aplicaciones de Office.
  
 **Los clientes de office 365 ProPlus:** Si su empresa está usando un plan de Office 365 que incluye Office 365 ProPlus, como el plan E3, el Skype para la aplicación empresarial se instala al mismo tiempo a los usuarios descargar e instalación Word, Excel, PowerPoint, etcetera. Esto también significa que no pueden desinstalar Skype para la empresa a menos que la todas las de Office desinstalación de.
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>Elija si desea permitir que Skype para la empresa esté disponible para los usuarios

Como el [Administrador](https://support.office.com/en-us/article/eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US) puede elegir si se debe permitir que el Skype para la aplicación empresarial esté disponible para los usuarios.
  
- **Para controlar si todas las personas de su compañía obtiene el software**: iniciar sesión en Office 365 centro de administración, vaya a **instalar el software**y, a continuación, seleccione el software que desea que esté disponible para los usuarios.
    
    ![Elija el software que desea poner a disposición de las personas de su compañía.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- **Para controlar si las personas de su compañía obtener el software**: iniciar sesión en Office 365 centro de administración, vaya a **los usuarios** > **usuarios activos**, seleccione la persona que desea conceder acceso al software y, a continuación, haga clic en **Editar** junto a **licencias de producto** y activar la licencia o desactivar.
    
    ![Elija qué software desea que el usuario tenga acceso a.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> Si necesita ver cuáles son los planes están asignados a personas de la organización, inicie sesión en el nuevo > de centro de administración de Office 365 **a los usuarios** > **usuarios activos**. Seleccione a la persona de la lista, a continuación, mire en **licencias de producto**. Si utiliza el centro de administración de Office 365 clásico, mire en la **licencia asignada**. 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>Implementación manual de Skype para la empresa a los usuarios
<a name="bkmk_manual_1"> </a>

Si desea que los usuarios que instalen el Skype para la aplicación empresarial desde una ubicación de la red en lugar de hacerlo desde Internet, puede descargar los archivos del programa de instalación. Para ello, vaya a la sección **implementación manual de software de usuario** del centro de administración de Office 365. A continuación, puede seleccionar **instalar** y guarde el archivo .exe del programa de instalación en una ubicación de red.
  
Otra opción consiste en descargar el Skype para una aplicación empresarial básico para los usuarios. Puede descargar [Microsoft Skype para Business Basic (32 o 64 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=49440).
  
Para ambos el básica y completa de Skype para aplicaciones empresariales, después de descargar los archivos del programa de instalación, necesitará enviar manualmente (por ejemplo, en el correo electrónico) la ruta de acceso de red a los usuarios para que pueden ejecutar el programa de instalación para instalar la aplicación en su equipo.
  
También puede usar estas descargas para implementar la Skype para la aplicación empresarial a los usuarios mediante el uso de los procesos y herramientas de implementación de software existente.
  
## <a name="for-larger-and-enterprise-organizations"></a>Para mayor y organizaciones empresariales

> [!NOTE]
> En esta sección solo se aplica a la Skype para la aplicación empresarial de disponible a través de los planes de Office 365. Si su organización usa una versión con licencia por volumen de la Skype para la aplicación empresarial, que está basada en Windows Installer (MSI), vea [Personalizar instalación del cliente en Skype para Business Server 2015](https://technet.microsoft.com/en-us/library/jj204934.aspx). 
  
En muchas empresas o grandes organizaciones, los usuarios no tienen permiso para instalar software en sus equipos. En su lugar, los departamentos de TI implementación el software necesario para los equipos de los usuarios. Los departamentos de TI también es posible que desee controlar la cantidad de ancho de banda de Internet o red que se usa en su organización, de modo que desean instalar software desde una ubicación de su red en lugar de hacerlo desde cercana a través de Internet o a través de la red corporativa.
  
Con Office 365, dispone de varias opciones para implementar la Skype para la aplicación empresarial si desea controlar donde se instala desde. Algunas de estas opciones incluyen lo siguiente:
  
- Descargue el Skype para la aplicación empresarial en su red local desde el centro de administración de Office 365, tal como se describe en [implementar manualmente Skype para la empresa a los usuarios](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1).
    
- Use la **[Herramienta de implementación de Office](https://go.microsoft.com/fwlink/p/?LinkID=626065)** para descargar Office 365 ProPlus o el Skype para la aplicación empresarial en su red local. A continuación, use la herramienta de implementación de Office para implementar la aplicación a los usuarios. La herramienta de implementación de Office le ofrece la posibilidad de controlar determinados aspectos de la implementación, como idiomas y la versión (32 bits o 64 bits).
    
- Use los existente de las herramientas de implementación de software y los procesos, como System Center Configuration Manager, para implementar Office 365 ProPlus o el Skype para la aplicación empresarial para los usuarios. Puede usar los procesos y herramientas existentes con la [Herramienta de implementación de Office](https://go.microsoft.com/fwlink/p/?LinkID=626065) o con el software que ha descargado desde el centro de administración de Office 365.
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>Obtener más información sobre el uso de la herramienta de implementación de Office

Para obtener información detallada acerca de cómo descargar la herramienta de implementación de Office y obtener más información acerca de cómo instalar el Skype para la aplicación empresarial y otras aplicaciones de cliente de Office 365, vea [administrar el software de usuario en Office 365](https://support.office.com/en-us/article/c13051e6-f75c-4737-bc0d-7685dcedf360).
  
Aquí es una visión general de los pasos necesarios para usar la herramienta de implementación de Office para implementar una aplicación:
  
1. **[Descargar la herramienta de implementación de Office más reciente](https://www.microsoft.com/en-us/download/details.aspx?id=49117)** de Microsoft Download Center.
    
2. Cree el archivo configuration.xml para usarse con la herramienta de implementación de Office que tiene la configuración de la aplicación de cliente que desee, como la configuración de la versión (32 bits o 64 bits), el idioma de instalación, etcetera.
    
3. Use la herramienta de implementación de Office y el archivo configuration.xml para descargar los archivos del programa de instalación en su red local o interna de la red de entrega de contenido (CDN) de Office.
    
4. Use la herramienta de implementación de Office y el configuration.xml para instalar las aplicaciones cliente de Office, incluidos el Skype para la aplicación empresarial de.
    
Para obtener información detallada sobre el uso de la herramienta de implementación de Office y el archivo configuration.xml, vea los siguientes artículos:
  
- [Información general sobre la herramienta de implementación de Office](https://technet.microsoft.com/library/jj219422.aspx)
    
- [Configuración de Configuration.Xml](https://technet.microsoft.com/library/jj219426.aspx)
    
### <a name="more-info-on-using-system-center-configuration-manager"></a>Obtener más información sobre el uso de System Center Configuration Manager

Puede usar los existente de las herramientas de implementación de software y los procesos, como System Center Configuration Manager, para implementar la Skype para la aplicación empresarial. Puede usar estas herramientas y procesos con ni el software que se descarga desde el centro de administración de Office 365 o con la herramienta de implementación de Office.
  
Para obtener más información acerca del uso de administrador de configuración para implementar software, vea los siguientes artículos:
  
- [Procedimiento para crear aplicaciones en el Administrador de configuración](https://technet.microsoft.com/en-us/library/gg682159.aspx)
    
- [Cómo implementar las aplicaciones en el Administrador de configuración](https://technet.microsoft.com/en-us/library/gg682082.aspx)
    
Si va a implementar el Skype para la aplicación empresarial como parte de la implementación de Office 365 ProPlus, vea [Implementar Office 365 ProPlus mediante el uso de System Center Configuration Manager](https://technet.microsoft.com/en-us/library/dn708063.aspx).
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>Planeación de las actualizaciones de la Skype para la aplicación empresarial

Como parte de la implementación de la Skype para la aplicación empresarial, debe tener en cuenta cómo desea obtener actualizaciones después de instalar Skype para la empresa. Estas actualizaciones pueden incluir las nuevas características, actualizaciones de seguridad o actualizaciones de seguridad comunes, como actualizaciones que proporcionan mejoras de estabilidad o rendimiento. Las dos cosas principales que debe tener en cuenta son:
  
- Donde desea obtener actualizaciones desde
    
- ¿Con qué frecuencia desea obtener las actualizaciones de la característica
    
Aunque puede controlar dónde obtener actualizaciones desde y ¿con qué frecuencia obtener las actualizaciones de la característica, no puede elegir qué actualizaciones de seguridad específicos o las actualizaciones de seguridad comunes que obtendrá.
  
 **Dónde obtener actualizaciones desde**
  
De forma predeterminada, una vez instalado el Skype para la aplicación empresarial, las actualizaciones se descargará automáticamente desde Internet cuando estén disponibles en Microsoft. Si desea tener más control sobre cuando las actualizaciones se produzcan o donde se instalan las actualizaciones desde, puede usar la herramienta de implementación de Office o la directiva de grupo para configurar.
  
Por ejemplo, muchas organizaciones desean actualizaciones con un grupo de usuarios de prueba antes de implementarlas en toda la organización. Puede hacerlo mediante la herramienta de implementación de Office o la directiva de grupo para configurar el Skype para la aplicación empresarial para obtener automáticamente las actualizaciones desde una ubicación específica de la red, en lugar de hacerlo desde Internet. A continuación, puede usar la herramienta de implementación de Office para descargar las actualizaciones de cada mes en su red local.
  
Para obtener más información acerca de cómo funcionan las actualizaciones de software de Office 365, vea estos artículos:
  
- [Información general del proceso de actualización de Office 365 ProPlus](https://technet.microsoft.com/en-us/library/dn761709.aspx)
    
- [Elija cómo administrar las actualizaciones de Office 365 ProPlus](https://technet.microsoft.com/en-us/library/dn761707.aspx)
    
- [Configurar las opciones de actualización para Office 365 ProPlus](https://technet.microsoft.com/en-us/library/dn761708.aspx)
    
  **La frecuencia de obtener actualizaciones de característica**
  
Además de dónde obtener actualizaciones desde, también puede controlar la frecuencia obtener nuevas características para la Skype para clientes empresariales. Las dos opciones son las siguientes:
  
- Obtener actualizaciones de característica cada mes, si hay características nuevas
    
- Obtener actualizaciones de características cada seis meses
    
Para algunas organizaciones desean tiempo para probar las características nuevas, por lo que desean obtener las actualizaciones de la característica solo dos veces al año en lugar de cada mes.
  
Puede controlar la frecuencia con obtener actualizaciones de característica mediante la herramienta de implementación de Office o la directiva de grupo para configurar el canal de actualización de. El proporciona mensual canal que la característica actualizaciones de todos los meses (aproximadamente), mientras que el canal delimitadas anual permite la característica actualizaciones cada seis meses. Para obtener más información acerca de los canales, vea [información general de los canales de actualización para Office 365 ProPlus](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4).
  
## <a name="related-topics"></a>Temas relacionados

[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)
  
[Licencias complementarias de Skype Empresarial y Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
