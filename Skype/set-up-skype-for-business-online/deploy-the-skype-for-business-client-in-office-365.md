---
title: "Implementar el cliente de Skype Empresarial en Office 365"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/21/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- httpsfix
- LeftNav_IT_O365
ms.assetid: 8c563b81-22c9-4024-9efe-9fe28c7bbc96
description: "Learn how to plan and deploy Skype for Business in small, medium, and large organizations and making it available to your users. "
---

# Implementar el cliente de Skype Empresarial en Office 365

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la [declinación de responsabilidades](8c563b81-22c9-4024-9efe-9fe28c7bbc96.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo [aquí](https://support.office.com/en-us/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96). 
  
En este artículo se explica cómo un **[Asignar roles de administrador en Office 365](http://technet.microsoft.com/library/eac4d046-1afd-4f1a-85fc-8219c79e1504%28Office.14%29.aspx)** puede implementar la aplicación Skype Empresarial a los usuarios de la organización.
  
Antes de implementar Skype Empresarial a los usuarios, asegúrese de que ha terminado los pasos 1 a 3, en el artículo [Configurar Skype Empresarial Online](set-up-skype-for-business-online.md). De este modo, Skype Empresarial se configurará con su dominio, todos los usuarios tendrán sus licencias y habrá configurado mensajería instantánea y [Configurar la presencia en Skype Empresarial Online](configure-presence-in-skype-for-business-online.md) para su organización.
  
> [!NOTE]
> Para que los usuarios instalar la aplicación Skype Empresarial, deben ser administradores locales en su equipo o dispositivo. O bien, tendrá que forme parte de un grupo local que puede instalar aplicaciones en su PC o dispositivos. Si los usuarios no pueden instalar software en sus dispositivos, debe instalar la aplicación de Skype Empresarial para ellos. 
  
## Para la mayoría de las empresas medianas o pequeñas

 **Instrucciones de instalación paso a paso:** Si tiene una pequeña o mediana empresa, le recomendamos simplemente pida a los usuarios para instalar la aplicación de Skype Empresarial en su PC. Dirigir a estas instrucciones:[Instalar Skype Empresarial](http://technet.microsoft.com/library/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb%28Office.14%29.aspx). Si están usando Mac, seleccione Configurar [Configurar Skype Empresarial para Mac 2011 para Office 365](http://technet.microsoft.com/library/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88%28Office.14%29.aspx). La aplicación Skype Empresarial se instala por separado desde el resto de las aplicaciones de Office.
  
 **Los clientes de office 365 ProPlus:** Si su empresa usa un plan de Office 365 que incluye Office 365 ProPlus, como el plan E3, se instala la aplicación Skype Empresarial al mismo tiempo, los usuarios descargar e instalación Word, Excel, PowerPoint, etcetera. Esto también significa que no pueden desinstalar Skype Empresarial a menos que desinstalación todos de Office.
  
### Elegir si Skype Empresarial estará disponible para los usuarios

Como [Asignar roles de administrador en Office 365](http://technet.microsoft.com/library/eac4d046-1afd-4f1a-85fc-8219c79e1504%28Office.14%29.aspx) puede elegir si desea hacer que la aplicación de Skype Empresarial disponibles para los usuarios.
  
- **Para controlar si todos los usuarios de su compañía obtiene el software**: inicie sesión en a la Centro de administración de Office 365, vaya a **instalar el software** y, a continuación, seleccione el software que desea que esté disponible para los usuarios.
    
    ![Choose the software you want to make available to the people in your company.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- **Para controlar si las personas de su empresa obtener el software**: inicie sesión en la Centro de administración de Office 365, vaya a **usuarios** > **usuarios activos**, seleccione la persona que desea conceder acceso al software y, a continuación, haga clic en **Editar** junto a ** Licencias de producto** y activar o desactivar el la licencia.
    
    ![Choose which software you want the user to access.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> Si necesita ver qué planes están asignados a las personas de su organización, inicie sesión en el nuevo Centro de administración de Office 365 > **usuarios** > **usuarios activos**. Seleccione a la persona de la lista, a continuación, busque en **licencias de producto**. Si está utilizando la clásica Centro de administración de Office 365, mire en **licencia asignada**. 
  
### Implementar de forma manual Skype Empresarial a los usuarios
<a name="bkmk_manual_1"> </a>

Si desea que los usuarios para instalar la aplicación de Skype Empresarial desde una ubicación de la red en lugar de desde Internet, puede descargar los archivos de instalación. Para ello, vaya a la sección **implementar manualmente el software de usuario** de la Centro de administración de Office 365. A continuación, puede seleccionar **instalar** y guardar el archivo .exe de instalación en una ubicación de red.
  
Otra opción es descargar la aplicación básica Skype Empresarial para los usuarios. Puede descargar [Microsoft Skype para Business Basic (32 o 64 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=49440).
  
Tanto las aplicaciones básicas y completo Skype Empresarial después de descargar los archivos de instalación, debe enviar manualmente (por ejemplo, en el correo electrónico) la ruta de acceso de red a los usuarios para que pueden ejecutar el programa de instalación para instalar la aplicación en su equipo.
  
También puede usar estas descargas para implementar la aplicación de Skype Empresarial a los usuarios con sus procesos y herramientas de implementación de software existentes.
  
## Para organizaciones empresariales de gran tamaño

> [!NOTE]
>  Esta sección solo es válida para la aplicación de Skype Empresarial disponible a través de los planes de Office 365. Si su organización usa una versión con licencia por volumen de la aplicación de Skype Empresarial, que está basada en Windows Installer (MSI), vea[Personalizar la instalación de clientes en Skype Empresarial Server 2015](https://technet.microsoft.com/es-es/library/jj204934.aspx). 
  
En muchas empresas o para grandes organizaciones, los usuarios no pueden instalar software en sus equipos. En su lugar, los departamentos de TI implementación el software necesario en equipos de los usuarios. Departamentos de TI también desee controlar la cantidad de ancho de banda de Internet o de red que utiliza en su organización, de modo que desean instalar software desde una ubicación cerca de su red en lugar de a través de Internet o a través de la red corporativa.
  
Con Office 365, tiene varias opciones para implementar la aplicación de Skype Empresarial si desea controlar donde está instalado desde. Algunas de estas opciones son las siguientes:
  
- Descargue la aplicación de Skype Empresarial a su red local desde el Centro de administración de Office 365, como se describe en [implementar manualmente Skype para la empresa a los usuarios](8c563b81-22c9-4024-9efe-9fe28c7bbc96.md#bkmk_manual).
    
- Use la **[Herramienta de implementación de Office](https://go.microsoft.com/fwlink/p/?LinkID=626065)** para descargar Office 365 ProPlus o la aplicación Skype Empresarial en su red local. A continuación, use la herramienta de implementación de Office para implementar la aplicación a los usuarios. La herramienta de implementación de Office le ofrece la capacidad de controlar ciertos aspectos de la implementación, como los idiomas y versión (32 bits o 64 bits).
    
- Use su procesos, como el Administrador de configuración de System Center y las herramientas de implementación de software existentes para implementar Office 365 ProPlus o la aplicación de Skype Empresarial a los usuarios. Puede usar los procesos y herramientas existentes con la [Herramienta de implementación de Office](https://go.microsoft.com/fwlink/p/?LinkID=626065) o con el software que ha descargado desde el Centro de administración de Office 365.
    
### Más información sobre el uso de la Herramienta de implementación de Office

Para obtener información sobre cómo descargar la Herramienta de implementación de Office y cómo instalar la aplicación de Skype Empresarial y otras aplicaciones cliente de Office 365, vea [Administrar el software de usuario en Office 365](http://technet.microsoft.com/library/365-c13051e6-f75c-4737-bc0d-7685dcedf360.aspx).
  
Aquí es una descripción general de los pasos implicados en el uso de la herramienta de implementación de Office para implementar una aplicación:
  
1. **[Descargue la herramienta de implementación de Office más reciente](https://go.microsoft.com/fwlink/p/?LinkID=626065)** desde Microsoft Download Center.
    
2. Cree el archivo configuration.xml para usarlo con la Herramienta de implementación de Office que tenga la configuración de la aplicación cliente que desea, como configurar la versión (32 o 64 bits), el idioma de instalación, etc.
    
3. Use la herramienta de implementación de Office y el archivo configuration.xml para descargar los archivos de instalación en su red local o interna de la red de entrega de contenido (CDN) de Office.
    
4. Use la herramienta de implementación de Office y la configuration.xml para instalar las aplicaciones cliente de Office, incluida la aplicación de Skype Empresarial.
    
Para obtener información sobre cómo usar la Herramienta de implementación de Office y el archivo configuration.xml, vea los artículos siguientes:
  
- [Información general de la Herramienta de implementación de Office](https://technet.microsoft.com/library/jj219422.aspx)
    
- [Configuración del archivo configuration.xml](https://technet.microsoft.com/library/jj219426.aspx)
    
### Más información sobre cómo usar el Administrador de configuración de System Center

Puede usar su procesos, como el Administrador de configuración de System Center y las herramientas de implementación de software existentes para implementar la aplicación Skype Empresarial. Puede usar estas herramientas y procesos con ni el software que se descarga de la Centro de administración de Office 365 o con la herramienta de implementación de Office.
  
Para obtener más información sobre cómo usar el Administrador de configuración para implementar el software, consulte los siguientes artículos:
  
- [Cómo crear aplicaciones en el Administrador de configuración](https://technet.microsoft.com/es-es/library/gg682159.aspx)
    
- [Cómo implementar aplicaciones en el Administrador de configuración](https://technet.microsoft.com/es-es/library/gg682082.aspx)
    
Si está implementando la aplicación Skype Empresarial como parte de la implementación de Office 365 ProPlus, vea [Implementar Office 365 ProPlus usando el Administrador de configuración de System Center](https://technet.microsoft.com/en-us/library/dn708063.aspx).
  
## Planear las actualizaciones de la aplicación de Skype Empresarial

Como parte de la implementación de la aplicación Skype Empresarial, debe tener en cuenta cómo desea obtener actualizaciones después de instala Skype empresarial. Estas actualizaciones pueden incluir características nuevas, actualizaciones de seguridad o actualizaciones de seguridad, como las actualizaciones que proporcionan mejoras de rendimiento o estabilidad. Los dos aspectos principales que debe tener en cuenta son:
  
- Donde desea obtener actualizaciones de
    
- ¿Con qué frecuencia desea obtener actualizaciones de características
    
Aunque puede controlar dónde obtener actualizaciones de y con qué frecuencia recibe actualizaciones de características, no puede elegir qué actualizaciones de seguridad específicos o seguridad no recibe.
  
 **Desde dónde descargar las actualizaciones**
  
De forma predeterminada, después de instala la aplicación Skype Empresarial, las actualizaciones se descargará automáticamente desde Internet cuando estén disponibles de Microsoft. Si desea tener más control sobre cuando se producen actualizaciones o cuando se instalan las actualizaciones de, puede usar la herramienta de implementación de Office o la directiva de grupo para configurar.
  
Por ejemplo, muchas organizaciones desean probar actualizaciones con un grupo de usuarios antes de la implementación de toda la organización. Puede hacer esto mediante la herramienta de implementación de Office o la directiva de grupo para configurar la aplicación de Skype Empresarial para obtener actualizaciones desde una ubicación específica de la red, en lugar de automáticamente desde Internet. A continuación, puede usar la herramienta de implementación de Office para descargar las actualizaciones de cada mes en su red local.
  
Para obtener más información sobre cómo funcionan las actualizaciones de software de Office 365, vea estos artículos:
  
- [Información general sobre el proceso de actualización de Office 365 ProPlus](https://technet.microsoft.com/library/dn761709.aspx)
    
- [Elija cómo administrar las actualizaciones de Office 365 ProPlus](https://technet.microsoft.com/en-us/library/dn761707.aspx)
    
- [Configuración de las opciones de actualización de Office 365 ProPlus](https://technet.microsoft.com/es-es/library/dn761708.aspx)
    
 **Frecuencia con que se obtienen las actualizaciones de características**
  
Además de dónde obtener actualizaciones de, también puede controlar la frecuencia con obtener nuevas características para la Skype empresarial Client. Las dos opciones son las siguientes:
  
- Obtener actualizaciones de características cada mes, si hay características nuevas
    
- Obtener actualizaciones de características cada seis meses
    
Para algunas organizaciones desean tiempo para probar nuevas características, por lo que desean obtener actualizaciones de características solo dos veces por año en lugar de cada mes.
  
Puede controlar la frecuencia con obtener actualizaciones de características mediante la herramienta de implementación de Office o la directiva de grupo para configurar el canal de actualización. El proporciona mensual canales que destacar actualizaciones mensual (aproximadamente), mientras que el canal de punto y anual permite características actualizaciones cada seis meses. Para obtener más información acerca de los canales, vea [información general de canales de actualización para Office 365 ProPlus](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4).
  
## Temas relacionados

[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)
  
[Skype para Business y Microsoft Teams licencias de complemento](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  

