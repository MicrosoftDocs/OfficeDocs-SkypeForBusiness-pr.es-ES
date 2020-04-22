---
title: Implementar el cliente de Skype empresarial en Microsoft 365 AOR Office 365
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
description: 'Aprenda a planificar e implementar Skype empresarial en organizaciones pequeñas, medianas y grandes y a poner a disposición de los usuarios. '
ms.openlocfilehash: d7c310935c5fa97873183d18b264616404471895
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777245"
---
# <a name="deploy-the-skype-for-business-client-in-microsoft-365-or-office-365"></a>Implementar el cliente de Skype empresarial en Microsoft 365 u Office 365

Este artículo explica las opciones para que el **[Administrador](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** pueda implementar la aplicación de Skype empresarial en las personas de su organización.
  
Antes de implementar Skype empresarial para los usuarios, asegúrese de que ha realizado los pasos 1-3 del artículo [configurar Skype empresarial online](set-up-skype-for-business-online.md). De esta manera, Skype empresarial se configurará con su dominio, todos tendrán sus licencias, habrá configurado la mensajería instantánea y configurar la [presencia en Skype empresarial online](configure-presence-in-skype-for-business-online.md) para su organización.
  
> [!NOTE]
> Para que los usuarios instalen la aplicación de Skype empresarial, deben ser administradores locales en su equipo o dispositivo. O bien, deberán formar parte de un grupo local que puede instalar aplicaciones en sus equipos o dispositivos. Si los usuarios no pueden instalar software en sus dispositivos, tendrá que instalar la aplicación de Skype empresarial para ellos. 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>Para la mayoría de las pequeñas y medianas empresas

 **Instrucciones de instalación paso a paso:** Si tiene una pequeña o mediana empresa, le recomendamos que simplemente pida a los usuarios que instalen la aplicación de Skype empresarial en su PC. Apunte a estas instrucciones: [instalar Skype empresarial](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb). Si están usando equipos Mac, selecciónelos para [configurar Lync para Mac 2011 para Office 365](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88). La aplicación de Skype empresarial se instala por separado en el resto de las aplicaciones de Office.
  
 **Aplicaciones de Microsoft 365 para clientes empresariales:** Si su empresa usa un plan 365 de Office que incluye aplicaciones de Microsoft 365 para empresas, como el plan E3, la aplicación de Skype empresarial se instala al mismo tiempo que los usuarios descargan e instalan Word, Excel, PowerPoint, etc. Esto también significa que no puede desinstalar Skype empresarial a menos que desinstale todo el Office.
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>Elegir si Skype empresarial estará disponible para los usuarios

Como [Administrador](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) , puede elegir si desea que la aplicación de Skype empresarial esté disponible para los usuarios.
  
- **Para controlar si todos los usuarios de su empresa obtienen el software**: inicie sesión en el centro de administración de Microsoft 365, vaya a **instalar mi software**y, a continuación, seleccione el software que quiere que estén disponibles para los usuarios.
    
    ![Elija el software que desea que esté disponible para los usuarios de su empresa.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- **Para controlar si determinadas personas de su empresa obtienen el software**: inicie sesión en el centro de administración de Microsoft 365, **vaya a** > **usuarios activos**, seleccione la persona a la que desea conceder acceso al software y, a continuación, haga clic en **Editar** junto a **licencias de producto** y Active o desactive la licencia.
    
    ![Elija el software al que desea que el usuario tenga acceso.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> Si necesita ver qué planes están asignados a las personas de su organización, inicie sesión en el centro de administración de Microsoft **365 >** > usuarios**activos**. Seleccione a la persona de la lista y, a continuación, busque en **licencias de producto**. Si está usando el centro de administración clásico, mire en **licencia asignada**. 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>Implementación manual de Skype empresarial para los usuarios
<a name="bkmk_manual_1"> </a>

Si desea que los usuarios instalen la aplicación de Skype empresarial desde una ubicación de la red en lugar de desde Internet, puede descargar los archivos de instalación. Para hacerlo, vaya a la sección **implementar manualmente el software de usuario** en el centro de administración de Microsoft 365. Después, puede seleccionar **instalar** y guardar el archivo Setup. exe en una ubicación de red.
  
Otra opción es descargar la aplicación básica de Skype empresarial para los usuarios. Puede descargar [Microsoft Skype empresarial Basic (32 o 64 bits)](https://www.microsoft.com/download/details.aspx?id=49440).
  
Tanto para las aplicaciones de Skype empresarial completas como básicas, una vez que haya descargado los archivos de instalación, tendrá que enviar de forma manual (por ejemplo, en un correo electrónico) la ruta de acceso de red a los usuarios para que puedan ejecutar el programa de instalación para instalar la aplicación en su equipo.
  
También puede usar estas descargas para implementar la aplicación de Skype empresarial a sus usuarios con las herramientas de implementación de software y los procesos existentes.
  
## <a name="for-larger-and-enterprise-organizations"></a>Para organizaciones empresariales grandes

> [!NOTE]
> Esta sección solo se aplica a la aplicación de Skype empresarial disponible en los planes de Office 365. Si su organización usa una versión con licencia por volumen de la aplicación de Skype empresarial, que se basa en Windows Installer (MSI), consulte [personalizar la instalación del cliente de Windows en Skype empresarial Server](https://technet.microsoft.com/library/jj204934.aspx).
  
En muchas empresas o organizaciones grandes, los usuarios no pueden instalar software en sus equipos. En su lugar, los departamentos de ti implementan el software necesario para los equipos de los usuarios. Los departamentos de ti también pueden querer controlar la cantidad de ancho de banda de Internet o de red que se usa en su organización, de modo que desean instalar software desde una ubicación cercana de su red en lugar de desde Internet o de toda la red corporativa.
  
Con Office 365, tiene varias opciones para implementar la aplicación de Skype empresarial si desea controlar desde dónde se instala. Algunas de estas opciones son las siguientes:
  
- Descargue la aplicación de Skype empresarial en su red local desde el centro de administración de Microsoft 365, como se describe en [implementar de forma manual Skype empresarial para los usuarios](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1).
    
- Use la **[herramienta de implementación de Office](https://go.microsoft.com/fwlink/p/?LinkID=626065)** para descargar las aplicaciones de Microsoft 365 para la empresa o la aplicación de Skype empresarial a su red local. A continuación, use la herramienta de implementación de Office para implementar la aplicación en los usuarios. La herramienta de implementación de Office le ofrece la posibilidad de controlar determinados aspectos de la implementación, como los idiomas y la versión (32 bits o 64 bits).
    
- Use los procesos y las herramientas de implementación de software existentes, como Microsoft Endpoint Configuration Manager, para implementar las aplicaciones de Microsoft 365 para la empresa o la aplicación de Skype empresarial a sus usuarios. Puede usar las herramientas y los procesos existentes con la [herramienta de implementación de Office](https://go.microsoft.com/fwlink/p/?LinkID=626065) o con el software que haya descargado desde el centro de administración de Microsoft 365.
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>Más información sobre el uso de la herramienta de implementación de Office

Para obtener información sobre cómo descargar la herramienta de implementación de Office y más información sobre cómo instalar la aplicación de Skype empresarial y otras aplicaciones cliente de Office 365, vea [administrar la configuración de descarga de software en Office 365](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360).
  
Aquí puede ver una descripción general de los pasos necesarios para usar la herramienta de implementación de Office para implementar una aplicación:
  
1. **[Descargue la herramienta de implementación de Office más reciente](https://www.microsoft.com/download/details.aspx?id=49117)** desde el centro de descarga de Microsoft.
    
2. Cree el archivo Configuration. XML para usarlo con la herramienta de implementación de Office que tiene la configuración de la aplicación cliente que desea, como establecer la versión (32 bits o 64 bits), el idioma de instalación, etc.
    
3. Use la herramienta de implementación de Office y el archivo Configuration. XML para descargar los archivos de configuración en su red local o interna desde la red de entrega de contenido (CDN) de Office.
    
4. Use la herramienta de implementación de Office y el archivo Configuration. XML para instalar las aplicaciones cliente de Office, incluida la aplicación de Skype empresarial.
    
Para obtener más información sobre el uso de la herramienta de implementación de Office y el archivo Configuration. XML, consulte los artículos siguientes:
  
- [Información general sobre la herramienta de implementación de Office](https://technet.microsoft.com/library/jj219422.aspx)
    
- [Configuración de Configuration. XML](https://technet.microsoft.com/library/jj219426.aspx)
    
### <a name="more-info-on-using-microsoft-endpoint-configuration-manager"></a>Más información sobre el uso de Microsoft Endpoint Configuration Manager

Puede usar los procesos y las herramientas de implementación de software existentes, como Microsoft Endpoint Configuration Manager, para implementar la aplicación de Skype empresarial. Puede usar estas herramientas y procesos con el software que descargue desde el centro de administración de Microsoft 365 o con la herramienta de implementación de Office.
  
Para obtener más información sobre cómo usar Configuration Manager para implementar software, vea los artículos siguientes:
  
- [Crear aplicaciones en Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/create-applications)
    
- [Implementar aplicaciones con Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
    
Si va a implementar la aplicación de Skype empresarial como parte de la implementación de las aplicaciones de Microsoft 365 para empresas, consulte [Administrar aplicaciones de microsoft 365 para la empresa con Configuration Manager](https://docs.microsoft.com/configmgr/sum/deploy-use/manage-office-365-proplus-updates).
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>Planear actualizaciones para la aplicación de Skype empresarial

Como parte de la implementación de la aplicación de Skype empresarial, debe tener en cuenta cómo desea obtener las actualizaciones después de instalar Skype empresarial. Estas actualizaciones pueden incluir nuevas características, actualizaciones de seguridad o actualizaciones no relacionadas con la seguridad, como las actualizaciones que proporcionan estabilidad o mejoras de rendimiento. Las dos cosas principales que debe considerar son:
  
- ¿Desde dónde desea obtener las actualizaciones?
    
- ¿Con qué frecuencia deseas obtener actualizaciones de características?
    
Aunque puede controlar desde dónde obtiene las actualizaciones y la frecuencia con la que obtiene actualizaciones de características, no puede elegir las actualizaciones de seguridad o las actualizaciones no relacionadas con la seguridad específicas que obtiene.
  
 **Desde dónde obtener las actualizaciones**
  
De forma predeterminada, después de instalar la aplicación de Skype empresarial, las actualizaciones se descargarán automáticamente de Internet cuando estén disponibles en Microsoft. Si desea tener más control sobre cuándo se producen las actualizaciones o desde dónde se instalan las actualizaciones, puede usar la herramienta de implementación de Office o la Directiva de grupo para configurarla.
  
Por ejemplo, muchas organizaciones desean probar las actualizaciones con un grupo de usuarios antes de implementarlas en toda la organización. Para ello, puede usar la herramienta de implementación de Office o la Directiva de grupo para configurar la aplicación de Skype empresarial con el fin de obtener actualizaciones desde una ubicación específica de la red, en lugar de hacerlo automáticamente desde Internet. Después, puede usar la herramienta de implementación de Office para descargar las actualizaciones todos los meses en la red local.
  
Para obtener más información sobre cómo funcionan las actualizaciones para el software de Office 365, consulte estos artículos:
  
- [Información general sobre el proceso de actualización de las aplicaciones de Microsoft 365 para empresas](https://technet.microsoft.com/library/dn761709.aspx)
    
- [Elegir cómo administrar las actualizaciones de las aplicaciones de Microsoft 365 para empresas](https://technet.microsoft.com/library/dn761707.aspx)
    
- [Configurar las opciones de actualización de las aplicaciones de Microsoft 365 para la empresa](https://technet.microsoft.com/library/dn761708.aspx)
    
  **Frecuencia con que se obtienen las actualizaciones de características**
  
Además de dónde obtiene las actualizaciones, también puede controlar la frecuencia con la que obtiene nuevas características para el cliente de Skype empresarial. Las dos opciones son las siguientes:
  
- Obtener actualizaciones de características todos los meses, si hay nuevas características
    
- Obtener actualizaciones de características cada seis meses
    
Para algunas organizaciones, quieren tener tiempo para probar nuevas características, por lo que quieren recibir actualizaciones de características solo dos veces al año en lugar de cada mes.
  
Puede controlar la frecuencia con que recibe las actualizaciones de características mediante la herramienta de implementación de Office o la Directiva de grupo para configurar el canal de actualización. El canal mensual le ofrece actualizaciones de características mensualmente (aproximadamente), mientras que el canal semianual le ofrece actualizaciones de características cada seis meses. Para obtener más información sobre los canales, vea [información general sobre los canales de actualización de las aplicaciones de Microsoft 365 para empresas](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4).
  
## <a name="related-topics"></a>Temas relacionados

[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)
  
[Licencias complementarias de Skype Empresarial y Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
