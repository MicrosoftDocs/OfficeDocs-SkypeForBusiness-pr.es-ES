---
title: Implementar el Skype para Business client en Office 365
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8c563b81-22c9-4024-9efe-9fe28c7bbc96
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 'Aprenda a planear e implementar Skype para empresas pequeñas, medianas y grandes empresas y ponerlo a disposición de los usuarios. '
ms.openlocfilehash: 83c2b0060f7edbb39c24709db2880b8aed014553
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="deploy-the-skype-for-business-client-in-office-365"></a>Implementar el Skype para Business client en Office 365

Este artículo explica las opciones de cómo, la **[administración](https://support.office.com/en-us/article/eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US)**, puede implementar el Skype para el negocio de la aplicación a las personas de su organización.
  
Antes de implementar Skype de negocio a los usuarios, asegúrese de que ha realizado los pasos 1-3 en el artículo [Configurar Skype para los negocios en línea](set-up-skype-for-business-online.md). De este modo, Skype para empresas se configurará con el dominio, todos los usuarios tendrán sus licencias y habrá configurado IM y [presencia de configurar en Skype para los negocios en línea](configure-presence-in-skype-for-business-online.md) para su organización.
  
> [!NOTE]
> Para que los usuarios que instalen el Skype para el negocio de la aplicación, deben ser administradores locales en sus PC o dispositivo. O necesitan formar parte de un grupo local que se puede instalar aplicaciones en sus PC o dispositivos. Si los usuarios no pueden instalar software en sus dispositivos, debe instalar el Skype para aplicaciones de negocio para ellos. 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>Para la mayoría de las empresas pequeña y medianas

 **Instrucciones de instalación paso a paso:** Si tiene una pequeña o mediana empresa, se recomienda pedir simplemente a los usuarios a instalar el Skype para el negocio de la aplicación en su PC. Remítales a estas instrucciones: [Instalar Skype para el negocio](https://support.office.com/en-us/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb?ui=en-US&rs=en-US&ad=US). Si están usando Macs, elija Configurar [Lync para Mac 2011 para Office 365](https://support.office.com/en-us/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88?ui=en-US&rs=en-US&ad=US). El Skype para el negocio de la aplicación se instala por separado del resto de las aplicaciones de Office.
  
 **Los clientes office 365 ProPlus:** Si su empresa utiliza un plan de Office 365 que incluye Office 365 ProPlus, como el plan E3, el Skype para el negocio de la aplicación se instala al mismo tiempo los usuarios descargar e instalan Word, Excel, PowerPoint, etcetera. Esto también significa que no pueden desinstalar Skype para el negocio, a menos que desinstalar todo Office.
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>Elija si desea disponer de Skype para el negocio de los usuarios

El [Administrador](https://support.office.com/en-us/article/eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US) puede elegir si desea poner el Skype para el negocio de la aplicación a disposición de los usuarios.
  
- **Para controlar si todas las personas de su empresa obtiene el software**: iniciar sesión en el Office 365 centro de administración, vaya a **instalar el software**y, a continuación, seleccione el software que desea que estén disponibles para los usuarios.
    
    ![Elija el software que desea poner a disposición de las personas de su empresa.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- **Para controlar si las personas de su empresa Obtén el software**: iniciar sesión en el Office 365 centro de admin, vaya a **usuarios** > **usuarios activos**, seleccione la persona que desea dar acceso al software y, a continuación, haga clic en **Editar** junto a **licencias de producto** y activar la licencia o desactivar.
    
    ![Elija el software que desea que el usuario tenga acceso.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> Si desea ver cuáles son los planes están asignados a las personas de su organización, iniciar sesión en el nuevo centro de administración de Office 365 > **usuarios** > **usuarios activos**. Seleccione a la persona de la lista, a continuación, busque en las **licencias de producto**. Si utiliza el centro de administración de Office 365 clásico, busque bajo **licencia asignada**. 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>Implementar manualmente Skype para el negocio de los usuarios
<a name="bkmk_manual_1"> </a>

Si desea que los usuarios a instalar el Skype para el negocio de la aplicación desde una ubicación de la red en lugar de hacerlo desde Internet, puede descargar los archivos de instalación. Para ello, vaya a la sección **implementar manualmente el software de usuario** del centro de administración de Office 365. A continuación, puede seleccionar **instalar** y guardar el archivo .exe de instalación en una ubicación de red.
  
Otra opción es descargar el Skype para Business Basic de la aplicación para los usuarios. Puede descargar [Microsoft Skype para Business Basic (32 o 64 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=49440).
  
Para ambos el básica y completa Skype para aplicaciones empresariales, después de haber descargado los archivos de instalación, deberá enviar manualmente (por ejemplo, en el correo electrónico) la ruta de acceso de red a los usuarios para que pueden ejecutar el programa de instalación para instalar la aplicación en su equipo.
  
También puede utilizar estas descargas para implementar el Skype para el negocio de la aplicación a los usuarios mediante los procesos y herramientas de implementación de software existente.
  
## <a name="for-larger-and-enterprise-organizations"></a>Para grandes organizaciones empresariales

> [!NOTE]
> Esta sección sólo se aplica a la Skype para la aplicación de negocio disponible a través de planes de Office 365. Si su organización utiliza una versión de licencia por volumen de la Skype para la aplicación de negocio, que está basada en Windows Installer (MSI), vea [Personalizar instalación del cliente de Skype para Business Server 2015](https://technet.microsoft.com/en-us/library/jj204934.aspx). 
  
En muchas empresas o para grandes organizaciones, los usuarios no están autorizados a instalar software en sus equipos. En su lugar, los departamentos de TI implementación el software necesario para los usuarios. Los departamentos de TI también es conveniente controlar la cantidad de ancho de banda de Internet o una red que utiliza en su organización, de modo que desean instalar software desde una ubicación en su red, en lugar de desde cercana a través de Internet o a través de la red corporativa.
  
Con Office 365, dispone de varias opciones para implementar el Skype para el negocio de la aplicación si desea controlar dónde se instala desde. Algunas de estas opciones son las siguientes:
  
- Descargar el Skype para la aplicación de negocio a la red local desde el centro de administración de Office 365, como se describe en [implementar manualmente Skype para el negocio a los usuarios](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1).
    
- Utilice la **[Herramienta de implementación de Office](https://go.microsoft.com/fwlink/p/?LinkID=626065)** para descargar Office 365 ProPlus o el Skype para la aplicación de negocio en la red local. A continuación, utilice la herramienta de implementación de Office para implementar la aplicación a los usuarios. La herramienta de implementación de Office le ofrece la posibilidad de controlar ciertos aspectos de la implementación, como los idiomas y la versión (32 bits o 64 bits).
    
- Usar sus herramientas de implementación de software existentes y procesos, como System Center Configuration Manager, para implementar Office 365 ProPlus o el Skype para el negocio de la aplicación a los usuarios. Puede utilizar los procesos y las herramientas existentes con la [Herramienta de implementación de Office](https://go.microsoft.com/fwlink/p/?LinkID=626065) o con el software que ha descargado desde el centro de administración de Office 365.
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>Obtener más información acerca de cómo utilizar la herramienta de implementación de Office

Para obtener más información acerca de cómo descargar la herramienta de implementación de Office y obtener más información acerca de cómo instalar el Skype para aplicaciones de negocios y otras aplicaciones de cliente de Office 365, vea [administrar el software de usuario en Office 365](https://support.office.com/en-us/article/c13051e6-f75c-4737-bc0d-7685dcedf360).
  
Presentamos una visión general de los pasos implicados en el uso de la herramienta de implementación de Office para implementar una aplicación:
  
1. **[Descargue la herramienta de implementación más recientes de Office](https://www.microsoft.com/en-us/download/details.aspx?id=49117)** desde Microsoft Download Center.
    
2. Crear el archivo configuration.xml para utilizarse con la herramienta de implementación de Office que tenga la configuración de la aplicación de cliente que desee, como la configuración de la versión (32 bits o 64 bits), el idioma de instalación, etcetera.
    
3. Utilice la herramienta de implementación de Office y el archivo configuration.xml para descargar los archivos de instalación en la red local o interna desde Office Content Delivery Network (CDN).
    
4. Utilice la herramienta de implementación de Office y el configuration.xml para instalar las aplicaciones cliente de Office, incluyendo el Skype para el negocio de la aplicación.
    
Para obtener más información acerca de cómo utilizar la herramienta de implementación de Office y el archivo configuration.xml, consulte los artículos siguientes:
  
- [Información general sobre la herramienta de implementación de Office](https://technet.microsoft.com/library/jj219422.aspx)
    
- [Configuración de Configuration.Xml](https://technet.microsoft.com/library/jj219426.aspx)
    
### <a name="more-info-on-using-system-center-configuration-manager"></a>Más información sobre el uso de System Center Configuration Manager

Puede utilizar sus herramientas de implementación de software existentes y procesos, como System Center Configuration Manager, para implementar el Skype para el negocio de la aplicación. Puede utilizar estas herramientas y procesos con ni el software que se descarga desde el centro de administración de Office 365, o con la herramienta de implementación de Office.
  
Para obtener más información acerca de cómo utilizar el Administrador de configuración para implementar software, consulte los artículos siguientes:
  
- [Cómo crear aplicaciones en el Administrador de configuración](https://technet.microsoft.com/en-us/library/gg682159.aspx)
    
- [Cómo implementar aplicaciones en Administrador de configuración](https://technet.microsoft.com/en-us/library/gg682082.aspx)
    
Si está implementando el Skype para la aplicación de negocio como parte de la implementación de Office 365 ProPlus, vea [Implementar Office 365 ProPlus utilizando System Center Configuration Manager](https://technet.microsoft.com/en-us/library/dn708063.aspx).
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>Planificación de actualizaciones para el Skype para el negocio de la aplicación

Como parte de la implementación de la Skype para el negocio de la aplicación, necesitará tener en cuenta cómo desea obtener actualizaciones después de instala Skype para el negocio. Estas actualizaciones pueden incluir nuevas características, actualizaciones de seguridad y actualizaciones de seguridad, como actualizaciones que proporcionan mejoras de rendimiento o estabilidad. Las dos cosas principales que debe tener en cuenta son:
  
- ¿Dónde desea obtener actualizaciones desde
    
- ¿Con qué frecuencia desea obtener las actualizaciones de la función
    
Aunque puede controlar dónde obtener actualizaciones desde y la frecuencia con la obtener actualizaciones de característica, no puede elegir qué actualizaciones de seguridad específicas o seguridad no obtendrá.
  
 **Dónde obtener actualizaciones desde**
  
De forma predeterminada, una vez instalado el Skype para el negocio de la aplicación, las actualizaciones se descargará automáticamente desde Internet cuando estén disponibles en Microsoft. Si desea más control sobre cuando se realizan actualizaciones o cuando se instalan las actualizaciones de, puede utilizar la herramienta de implementación de Office o la directiva de grupo para configurar.
  
Por ejemplo, muchas organizaciones desean actualizaciones con un grupo de usuarios de prueba antes de implementarlas en toda la organización. Puede hacerlo mediante la herramienta de implementación de Office o la directiva de grupo para configurar el Skype para el negocio de la aplicación para obtener automáticamente actualizaciones desde una ubicación específica de la red, en lugar de hacerlo desde Internet. A continuación, puede utilizar la herramienta de implementación de Office para descargar las actualizaciones de cada mes a la red local.
  
Para obtener más información acerca de cómo funcionan las actualizaciones para el software de Office 365, vea estos artículos:
  
- [Información general sobre el proceso de actualización de Office 365 ProPlus](https://technet.microsoft.com/en-us/library/dn761709.aspx)
    
- [Elegir cómo desea gestionar las actualizaciones de Office 365 ProPlus](https://technet.microsoft.com/en-us/library/dn761707.aspx)
    
- [Configurar las opciones de actualización para Office 365 ProPlus](https://technet.microsoft.com/en-us/library/dn761708.aspx)
    
 **La frecuencia de obtener actualizaciones de la función**
  
Además de dónde obtener actualizaciones desde, también puede controlar qué frecuencia recibes nuevas características para el Skype para cliente de empresa. Las dos opciones son las siguientes:
  
- Obtener actualizaciones de característica cada mes, si hay características nuevas
    
- Obtener actualizaciones de características cada seis meses
    
Para algunas organizaciones quieren tiempo para probar nuevas características, por lo que desean obtener actualizaciones de función sólo dos veces al año en lugar de cada mes.
  
Puede controlar la frecuencia con obtener actualizaciones de función utilizando la herramienta de implementación de Office o la directiva de grupo para configurar el canal de actualización. El proporciona canal mensual que cuentan con actualizaciones mensuales (aproximadamente), mientras que el canal semestral permite cuentan con actualizaciones cada seis meses. Para obtener más información acerca de los canales, vea [información general acerca de los canales de actualización para Office 365 ProPlus](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4).
  
## <a name="related-topics"></a>See also

[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)
  
Puede obtener más información en [Conferencias de acceso telefónico en Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
  
 
