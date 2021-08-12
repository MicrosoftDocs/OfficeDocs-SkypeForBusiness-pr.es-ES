---
title: Implementar Skype conectividad en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 'Summary: Learn how to connect Skype Empresarial Server with Skype consumer. También se conoce como Skype conectividad.'
ms.openlocfilehash: 752bae0797da1129d677dd962ad9dc6e4b9a6e99123babcf30ab8bd11bdbf668
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307791"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>Implementar Skype conectividad en Skype Empresarial Server

**Resumen:** Obtenga información sobre cómo conectarse Skype Empresarial Server con Skype cliente. También se conoce como Skype conectividad.
  
En este artículo se guía por la implementación para Skype conectividad.
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Skype Información general sobre conectividad para profesionales de TI

Skype La conectividad proporciona Skype Empresarial usuarios con la capacidad de buscar y agregar Skype usuarios. Skype La conectividad es una característica de Skype Empresarial que permite habilitar la búsqueda de federación y directorio con Skype usuarios. Después de habilitar Skype conectividad, Skype Empresarial los usuarios podrán buscar y agregar Skype usuarios.
  
## <a name="skype-directory-search"></a>Skype Búsqueda de directorios

Skype La funcionalidad de búsqueda de directorios Skype Empresarial usuarios con la capacidad de buscar Skype contactos. La funcionalidad de búsqueda permite a los usuarios buscar con lo siguiente:
  
- **Buscar por nombre para mostrar, ejemplo "John Doe":** esto podría devolver muchos resultados, por lo que es posible que no encuentre lo que está buscando.
    
- Búsqueda por nombre para mostrar más ubicación, ejemplo **"John Doe en Barcelona":** esto limitará considerablemente los resultados de la búsqueda.
    
- **Búsqueda por correo electrónico, ejemplo "johndoe@outlook.com":** esto debe devolver un resultado en la mayoría de los casos; el que coincide exactamente con el correo electrónico especificado. Pero si el mismo correo electrónico está asociado a más de una cuenta, se pueden devolver varios resultados.
    
- **Buscar por número de teléfono, ejemplo "123-123-1234":** esto debería devolver un resultado en la mayoría de los casos; el que coincide exactamente con el teléfono especificado. Teléfono número debe incluir el código de país (es decir, 1-xxx-yyy-zzzz). Si el mismo número de teléfono está asociado a más de una cuenta, se pueden devolver varios resultados.
    
- **Search by Skype Name, example "JohnDoe1456"** - If exact match is found, it will be returned as the first result. Se pueden devolver otras posibles coincidencias de "nombre".
    
    > [!NOTE]
    > Skype La búsqueda de directorios debe poder comunicarse con las siguientes direcciones IP en el puerto 443: 104.40.75.246, 23.101.135.34 y 40.113.86.19. 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Matriz de implementación compatible para Skype búsqueda de directorios

En la tabla siguiente se describe la compatibilidad Skype búsqueda de directorios.
  

||**Skype Empresarial Server Front-End**|**Front-End de Lync Server 2013 (o versiones anteriores)**|**Comments**|
|:-----|:-----|:-----|:-----|
|Skype Empresarial Server Edge  <br/> |Compatible  <br/> |No se admite  <br/> |Skype Empresarial Server y Edge son requisitos previos para la Skype búsqueda de directorios  <br/> |
|Skype Empresarial Server Edge + Lync Server 2013 Edge implementados en paralelo  <br/> |Compatible  <br/> |No se admite  <br/> |Skype El tráfico de búsqueda de directorios fluye Skype Empresarial Server servidores perimetrales. El tráfico de federación pasa por el perímetro configurado por el administrador. Por ejemplo, el administrador podría optar por continuar con el envío de tráfico de federación a través de servidores perimetrales de Lync Server 2013 que no admitirían la búsqueda Skype directorio.  <br/> |
|Lync Server 2013 (o versiones anteriores) perimetral  <br/> |No se admite  <br/> |No se admite  <br/> ||
   
> [!NOTE]
> El servicio de libreta de direcciones que se ejecuta en Skype Empresarial Server front-end encuentra el servidor perimetral por la existencia del puerto de búsqueda Skype 4443 en el servidor perimetral. 
  
> [!NOTE]
> En caso de que un cliente tenga varios sitios en su implementación local y si ha implementado solo un servidor perimetral o grupo de servidores perimetrales de Skype Empresarial Server, el tráfico de búsqueda de todos los sitios pasará por el único servidor perimetral disponible. El administrador debe asegurarse de que los grupos de servidores de todos los sitios puedan tener acceso al servidor perimetral o grupo Skype Empresarial Server implementado. 
  
> [!NOTE]
> Skype de gráficos limitará las solicitudes de búsqueda de cualquier cliente local o Microsoft 365 o Office 365 si la tasa de solicitudes supera las 15 solicitudes por segundo. 
  
> [!NOTE]
> Para los clientes locales de grandes empresas, los dominios tendrán que agregarse a una lista de permitidos con el servicio de búsqueda Skype para permitir tasas de solicitudes más altas.
  
> [!NOTE]
> Skype Empresarial Server limitará las solicitudes entrantes, si hay demasiadas solicitudes pendientes en la cola. 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online"></a>Implementación de Skype conectividad para Skype Empresarial Online

Skype La conectividad también es una característica de Skype Empresarial Online, que forma parte de Microsoft 365 y Office 365. Puede habilitar la característica Skype conectividad desde el Centro Skype Empresarial administración en el Centro de administración de Microsoft 365.
  
For Microsoft 365 Midsize Business, Office 365 Enterprise, Microsoft 365 Educación, and Office 365 for Government: Sign in to the Centro de administración de Microsoft 365 and navigate to the Skype Empresarial Administration Center. Vaya a Comunicaciones externas. En Proveedores de servicios de mensajería instantánea pública, haga clic en Habilitar. Si desea controlar el acceso de usuarios individuales a Skype conectividad, puede hacerlo editando la configuración de comunicaciones externas de los usuarios individuales.
  
Para Office 365 Pequeña Empresa Premium: inicie sesión en Office 365 y vaya a Servicio de administración Configuración mensajería instantánea, reuniones \> \> y conferencias. Activar comunicaciones externas. El conmutador de comunicaciones externas activa tanto Skype conectividad como las comunicaciones con otras organizaciones que usan Skype Empresarial.
  
Para obtener más información sobre Skype Empresarial administración en línea, vea:
  
- [Permitir a los usuarios contactar con usuarios externos de Skype Empresarial](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [Qué probar si no puedes realizar mi Skype Empresarial o Skype contactos externos](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [Agregar un contacto en Skype Empresarial](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [Administradores: configurar Skype Empresarial configuración para usuarios individuales](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>Implementación de Skype conectividad para Skype Empresarial Server

Skype Empresarial Server la arquitectura de acceso de federación para admitir la conectividad con Skype. Esta conectividad permite a los Skype Empresarial Server usuarios agregar Skype. Skype clientes también pueden agregar Skype Empresarial usuarios a su lista de contactos. Según las directivas establecidas administrativamente en Skype Empresarial Server los usuarios podrán comunicarse con mensajería instantánea, ver la presencia de los demás e iniciar llamadas de audio y vídeo. Skype conectividad es también una característica de Skype Empresarial Online y se puede habilitar para clientes de Skype Empresarial Online desde el Centro de administración de Skype Empresarial dentro del Centro de administración de Microsoft 365.
  
> [!NOTE]
> Si Skype Empresarial Server ya está configurado para conectarse con Windows Messenger mediante la conectividad de mensajería instantánea pública (PIC), la implementación ya está configurada para la Skype conectividad. El único cambio que puede considerar es cambiar el nombre de la entrada pic de Messenger existente como Skype. 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>El Skype Empresarial Server de aprovisionamiento de conectividad de mensajería instantánea pública ya no está disponible

El sitio que anteriormente se usaba para aprovisionar manualmente la federación entre Skype Empresarial implementaciones locales y Skype ya no es necesario y se cerrará el 15/8/2019. La federación Skype ahora usa la detección de partners federados, que es el mismo mecanismo necesario para la federación con Skype Empresarial Online.

La comunicación entre cualquier implementación Skype Empresarial local y los usuarios de Skype a través de la infraestructura de mensajería instantánea pública existente ahora requiere que la configuración del servidor perimetral local sea compatible con Skype Empresarial Online.

> [!NOTE]
> La mayoría de los clientes no necesitan ninguna acción, incluidas todas las implementaciones federadas con Skype Empresarial Online.
  
Las implementaciones locales son necesarias para publicar un registro SRV dns de federación para cada dominio que hospedan. Las instrucciones están disponibles en [la planeación de DNS.](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning) Cada dominio debe resolverse mediante una consulta SRV dns en un FQDN de servidor perimetral que satisfaga una coincidencia de sufijos de nivel superior del dominio. Por ejemplo, considere el dominio "contoso.com":

|**FQDN válidos**|**Comment**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |En cada caso, el FQDN exacto debe estar presente en el SN o el SAN del certificado externo instalado en el servidor perimetral.   |
|access.contoso.com   ||
|**FQDN no válidos**|**Motivo**|
|sip.contoso-edge.com   |No es una coincidencia de sufijo.  |
|sip.it.contoso.com   |No coincide con un sufijo de nivel superior.   |

Puede encontrar más instrucciones sobre certificados externos en [Planeación de certificados.](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning)

#### <a name="faqs"></a>Preguntas frecuentes

**¿Por qué se está cerrando el sitio web de aprovisionamiento?**
El mecanismo de aprovisionamiento de mensajería instantánea (PIC) público (pic.lync.com) que se implementó en 2006 ya no es serviceable y se cerrará el 15/8/2019. En su lugar, la federación de mensajería instantánea pública asumirá el mismo modelo de federación usado por Skype Empresarial Online, conocido como "detección de partners", por el que una implementación local es públicamente detectable por sus registros SRV DNS de federación.

**¿Este cambio significa que la federación de mensajería instantánea pública está en desuso?**
No. La federación de mensajería instantánea pública seguirá siendo compatible durante muchos años, probablemente hasta que Skype Empresarial producto local llegue al final de su vida útil.

**Nuestra empresa tiene una relación híbrida (espacio de direcciones compartido) con Skype Empresarial Online, ¿nos vemos afectados?**
No, dado que ya está federando con Skype Empresarial Online, este cambio no le afectará.
 
**¿Este cambio significa que nuestra empresa tiene que habilitar la federación con Skype Empresarial Online?**
No. Si la configuración de proxy del servidor perimetral no habilita la federación con el proveedor de hospedaje de Skype Empresarial Online (sipfed.online.lync.com), este cambio no afectará a eso. Sin embargo, los mismos requisitos de CERTIFICADO y DNS que se aplican a la federación con Skype Empresarial Online ahora también se aplican a la federación con Skype usuarios.
 
**Nuestra empresa es grande y no puede cambiar su configuración perimetral debido a motivos normativos/de cumplimiento/etc... ¿Qué podemos hacer?**
Cualquier organización local que no pueda cambiar su configuración del servidor perimetral según se especifique, debe comunicarse con el soporte técnico del producto lo antes posible.

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>Habilitar la federación y la conectividad de mensajería instantánea pública (PIC)

Ahora, céntrate en el entorno Skype Empresarial Server y las tareas administrativas necesarias para configurar Skype conectividad. En esta sección, se supone que el administrador ha implementado Skype Empresarial Server y configurado el acceso externo, también conocido como servidores perimetrales. 
  
Hay tres pasos principales necesarios para habilitar la federación y pic. Estos son:
  
1. Configurar federación y PIC
    
2. Configurar al menos una directiva para admitir el acceso de usuarios federados
    
3. Configurar la configuración Skype proveedor de PIC
    
#### <a name="1-configure-federation-and-pic"></a>1. Configurar federación y PIC

La federación es necesaria para permitir que Skype usuarios se comuniquen con Skype Empresarial usuarios de la organización. La conectividad de mensajería instantánea (PIC) pública es una clase de federación y debe configurarse para permitir que los usuarios Skype Empresarial se comuniquen con Skype usuarios. La federación y pic se configuran mediante el panel Skype Empresarial Server control.
  
> [!NOTE]
> La federación de PIC ya no es compatible con las versiones de productos anteriores a Lync Server 2010 (Live Communication Server, Office Communications Server). Las plataformas admitidas para la federación PIC incluyen Skype Empresarial Server, Lync Server 2013 y Lync Server 2010. 
  
La federación es necesaria para permitir que Skype usuarios se comuniquen con Skype Empresarial usuarios de la organización. La conectividad de mensajería instantánea (PIC) pública es una clase de federación y debe configurarse para permitir que los usuarios de Skype Empresarial Server puedan comunicarse con Skype usuarios. La federación y pic se configuran mediante el cuadro de diálogo Configuración perimetral del panel de control Skype Empresarial Server como se muestra en la figura.
  
![Definir nuevo grupo de servidores perimetrales](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> Los atributos EnableSkypeIdRouting y EnableSkypeDirectorySearch deben establecerse en true en la configuración del proveedor público (consulte las instrucciones posteriores) para que la búsqueda funcione. 
  
Esto completa las tareas administrativas que deben realizarse en el servidor. Ahora está configurado para la Skype conectividad.
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. Configurar al menos una directiva para admitir el acceso de usuarios federados

Con el Panel de control Skype Empresarial Server, un administrador debe configurar una o más directivas de acceso de usuarios externos para controlar si Skype usuarios pueden colaborar con usuarios Skype Empresarial Server usuarios internos.
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. Configurar la configuración Skype proveedor de PIC

Con el Shell Skype Empresarial Server administración, un administrador debe configurar la directiva de cliente Skype Empresarial para mostrar Skype como un proveedor pic adicional. 
  
> [!NOTE]
> Los usuarios de los proveedores de servicios de conectividad de mensajería instantánea (PIC) no pueden participar en mensajería instantánea o conferencias en su organización hasta que también configure al menos una directiva (paso 2, anterior a este procedimiento) para admitir la conectividad de mensajería instantánea pública. 
  
Para las nuevas instalaciones, puede configurar Skype conectividad mediante la habilitación de un proveedor Skype público mediante el Panel de control Skype Empresarial Server como se muestra en la figura.
  
![Proveedores federados SIP](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> Para configurar Skype conectividad al actualizar a Skype Empresarial Server debe quitar y volver a agregar el proveedor público Skype existente. 
  
La configuración Skype conectividad también se puede realizar con PowerShell únicamente. Para configurar Skype conectividad mediante PowerShell:
  
1. Desde un Skype Empresarial Server front-end, abra el Shell Skype Empresarial Server administración.
    
2. Ejecute los dos comandos siguientes:
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > Si todavía no tiene un proveedor de PIC en su entorno y está creando un nuevo proveedor de PIC, no es necesario ejecutar el cmdlet Remove-CsPublicProvider. 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    ¿Qué hacen los parámetros menos obvios?
    
   - ProxyFqdn: ubicación de Skype de federación (propiedad/mantenida por Microsoft)
    
   - IconURL: icono usado por lync &amp; Skype Empresarial cliente para identificar visualmente Skype contactos
    
   - NameDecorationRoutingDomain y NameDecorationExcludedDomainList: esta configuración permite Skype a los usuarios escribir MSA de los usuarios sin necesidad de "decorar" dominios que no son de Microsoft con "msn.com". Esto elimina la necesidad de escribir "user(contoso.com)@msn.com" para todos los dominios QUE NO están en excludedDomainList. El cliente SfB dará formato automáticamente a la MSA si el dominio NO está en la lista Excluidos. Hemos agregado los dominios de cuenta de Microsoft más comunes a la lista excluida.
    
     > [!NOTE]
     > El proveedor público debe quitarse y agregarse nuevo si se realizan cambios. No se permiten cambios en la configuración local. 
  
     > [!NOTE]
     > Agregado en el cliente de escritorio de Lync Server 2013 CU5 en &amp; Office 2013 SP1, NameDecorationRoutingDomain y NameDecorationExcludedDomainList mejoran la situación en la que los usuarios de Lync agregan contactos Skype necesarios para "decorar" dominios que no son de Microsoft para identificarlos y enrutrlos a Skype (el formato de: user(contoso.com)@msn.com). Esta nueva configuración permitirá el formato automático de la dirección que el usuario escribe en el cuadro de diálogo "Agregar contacto de Skype" con nameDecorationRoutingDomain (que debe establecerse en msn.com) si no contiene los dominios del NameDecorationExcludedDomainList (actualmente podemos admitir msn.com, live.com, Hotmail.com, outlook.com). 
  
3. Desde un Skype Empresarial los usuarios cliente ahora pueden buscar y agregar un Skype usuario.
    
## <a name="clients-and-interoperability-matrix"></a>Clientes y matriz de interoperabilidad

En la tabla siguiente se describe el estado de interoperabilidad entre la última versión de Skype consumidor y la versión más reciente de Skype Empresarial.
  

|**Skype Clientes**|**Agregar contactos, mensajería instantánea, presencia, audio y videollamadas**|**Comment**|
|:-----|:-----|:-----|
|Skype Windows escritorio  <br/> |7.6 o superior, Windows XP y versiones posteriores  <br/> |**NUEVO:** compatibilidad agregada para Windows Skype cliente que se ejecuta en Windows XP y Windows Vista (requiere la versión **7.26 del** cliente más reciente o posterior) <br/> |
|Skype Móvil: androide Teléfono y tableta  <br/> |6.19 o posterior, ejecutando Android OS versión 4.0.3 o posterior  <br/> |Es posible que los dispositivos de especificaciones bajas no admitan llamadas de vídeo  <br/> |
|Skype Móvil: iOS  <br/> |6.11 o superior, en IOS 7 o posterior  <br/> |No se admiten iPhone 4 y versiones anteriores, la 4ª generación del iPod y versiones anteriores, iPad 1ª generación  <br/> |
|Skype Mac  <br/> |7.19 o superior, en Mac OS X 10.9 (Mavericks) o posterior  <br/> |Requiere Mac OSX 10.9 o posterior  <br/> |
|Skype Aplicación Windows universal (Windows 10) escritorio y móvil  <br/> |Windows 10 (actualización de Redstone 1 o posterior)  <br/> |Windows La aplicación universal recibirá la actualización en otoño de 2016 agregando compatibilidad con interoperabilidad  <br/> |
   
En la tabla siguiente se describe el estado de interoperabilidad entre la última versión de Skype Empresarial y la versión más reciente de Skype consumidor. 
  
|**Cliente**|**Skype Búsqueda de directorios y agregar contactos**|**Skype A/V, interoperabilidad de mensajería instantánea**|
|:-----|:-----|:-----|
|Skype for Business  <br/> |Sí  <br/> |Sí  <br/> |
|Skype Empresarial en Mac  <br/> |Puede agregar (sin búsqueda)  <br/> |Sí  <br/> |
|Lync Desktop 2013  <br/> |Puede agregar (sin búsqueda)  <br/> |Sí  <br/> |
|Lync Web App: en línea y local  <br/> |N/D  <br/> |N/D  <br/> |
|Lync Mobile: Windows Phone  <br/> |Próximamente.  <br/> |Sí  <br/> |
|Lync Mobile - Android  <br/> |Próximamente.  <br/> |Sí  <br/> |
|Lync Mobile: iOS  <br/> |Próximamente.  <br/> |Sí  <br/> |
|Sistema Lync Room  <br/> |Próximamente.  <br/> |Sí  <br/> |
|Aplicación moderna de Lync (Win 8.1)  <br/> |Sí  <br/> |Sí  <br/> |
|Lync Mac 2011  <br/> |Puede agregar (sin búsqueda)  <br/> |Sí  <br/> |
|Lync Desktop 2010  <br/> |Puede agregar (sin búsqueda)  <br/> |Sí  <br/> |
|Lync Phone Edition  <br/> |N/D  <br/> |N/D  <br/> |
|Operador de Lync  <br/> |N/D  <br/> |N/D  <br/> |
   
