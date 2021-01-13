---
title: Implementar la conectividad de Skype en Skype Empresarial Server
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
description: 'Resumen: obtenga información sobre cómo conectar Skype Empresarial Server con el consumidor de Skype. También se conoce como conectividad de Skype.'
ms.openlocfilehash: ae3982375c0693c34e204e4512481a1f9f3b6ec3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834110"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>Implementar la conectividad de Skype en Skype Empresarial Server

**Resumen:** Obtenga información sobre cómo conectar Skype Empresarial Server con el consumidor de Skype. También se conoce como conectividad de Skype.
  
En este artículo se describe la implementación de conectividad de Skype.
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Introducción a la conectividad de Skype para profesionales de TI

La conectividad de Skype proporciona a los usuarios de Skype Empresarial la capacidad de buscar y agregar usuarios de Skype. La conectividad de Skype es una característica de Skype Empresarial que le permite habilitar la federación y la búsqueda en directorios con usuarios de Skype. Después de habilitar la conectividad de Skype, los usuarios de Skype Empresarial podrán buscar y agregar usuarios de Skype.
  
## <a name="skype-directory-search"></a>Búsqueda en el directorio de Skype

La funcionalidad de búsqueda de directorios de Skype proporciona a los usuarios de Skype Empresarial la capacidad de buscar contactos de Skype. La funcionalidad de búsqueda permite a los usuarios buscar con lo siguiente:
  
- **Buscar por nombre para mostrar, ejemplo "John Doe":** esto podría devolver muchos resultados, por lo que es posible que no encuentre lo que está buscando.
    
- **Buscar por nombre para mostrar más ubicación, por ejemplo "John Doe in Madrid":** esto limitará considerablemente los resultados de la búsqueda.
    
- **Buscar por correo electrónico, ejemplo "johndoe@outlook.com":** esto debería devolver un resultado en la mayoría de los casos; el que coincide exactamente con el correo electrónico especificado. Pero si el mismo correo electrónico está asociado a más de una cuenta, pueden devolverse varios resultados.
    
- **Buscar por número de teléfono, ejemplo "123-123-1234":** esto debería devolver un resultado en la mayoría de los casos; el que coincide exactamente con el teléfono especificado. El número de teléfono debe incluir el código de país (es decir, 1-xxx-yyy-zzzz). Si el mismo número de teléfono está asociado a más de una cuenta, pueden devolverse varios resultados.
    
- **Buscar por nombre de Skype, ejemplo "JohnDoe1456":** si se encuentra una coincidencia exacta, se devolverá como primer resultado. Se pueden devolver otras posibles coincidencias de "nombre".
    
    > [!NOTE]
    > La búsqueda en directorios de Skype debe poder comunicarse con las siguientes direcciones IP en el puerto 443: 104.40.75.246, 23.101.135.34 y 40.113.86.19. 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Matriz de implementación compatible con la búsqueda en directorios de Skype

En la tabla siguiente se describe la compatibilidad con la búsqueda de directorios de Skype.
  

||**Front-end de Skype Empresarial Server**|**Front-end de Lync Server 2013 (o anterior)**|**Comments**|
|:-----|:-----|:-----|:-----|
|Perímetro de Skype Empresarial Server  <br/> |Compatible  <br/> |No se admite  <br/> |Skype Empresarial Server y Edge son requisitos previos para la búsqueda en directorios de Skype  <br/> |
|Perímetro de Skype Empresarial Server + Servidor perimetral de Lync Server 2013 implementado en paralelo  <br/> |Compatible  <br/> |No se admite  <br/> |El tráfico de búsqueda de directorios de Skype fluye a través de los servidores perimetrales de Skype Empresarial Server. El tráfico de federación pasa a través del perímetro configurado por el administrador. Por ejemplo, el administrador podría optar por continuar con el envío de tráfico de federación a través de servidores perimetrales de Lync Server 2013 que no admitirían la búsqueda en directorios de Skype.  <br/> |
|Servidor perimetral de Lync Server 2013 (o anterior)  <br/> |No se admite  <br/> |No se admite  <br/> ||
   
> [!NOTE]
> El servicio de libreta de direcciones que se ejecuta en el front-end de Skype Empresarial Server encuentra el servidor perimetral por la existencia del puerto de búsqueda de Skype 4443 en el servidor perimetral. 
  
> [!NOTE]
> En caso de que un cliente tenga varios sitios en su implementación local y si solo ha implementado un servidor perimetral o un grupo de servidores perimetrales de Skype Empresarial Server, el tráfico de búsqueda de todos los sitios pasará por el único servidor perimetral disponible. El administrador debe asegurarse de que los grupos de servidores de todos los sitios pueden acceder al servidor perimetral o grupo de servidores perimetrales de Skype Empresarial Server implementado. 
  
> [!NOTE]
> El servicio de Gráfico de Skype limitará las solicitudes de búsqueda de cualquier cliente local o de Microsoft 365 u Office 365 si la tasa de solicitudes supera las 15 solicitudes por segundo. 
  
> [!NOTE]
> Para los clientes locales de grandes empresas, los dominios tendrán que estar en la lista blanca con el servicio de búsqueda de Skype para permitir mayores tasas de solicitudes. 
  
> [!NOTE]
> Skype Empresarial Server limitará las solicitudes entrantes, si hay demasiadas solicitudes pendientes en la cola. 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online"></a>Implementación de la conectividad de Skype para Skype Empresarial Online

La conectividad de Skype también es una característica de Skype Empresarial Online, que forma parte de Microsoft 365 y Office 365. Puede habilitar la característica Conectividad de Skype desde el Centro de administración de Skype Empresarial en el Centro de administración de Microsoft 365.
  
Para Microsoft 365 Mediana Empresa, Office 365 Enterprise, Microsoft 365 Educación y Office 365 para la Administración Pública: inicie sesión en el Centro de administración de Microsoft 365 y vaya al Centro de administración de Skype Empresarial. Vaya a Comunicaciones externas. En Proveedores de servicios de mensajería instantánea pública, haga clic en Habilitar. Si desea controlar el acceso de usuarios individuales a la conectividad de Skype, puede hacerlo editando la configuración de comunicaciones externas de los usuarios individuales.
  
Para Office 365 Pequeña Empresa Premium: inicie sesión en Office 365 y vaya a Configuración del servicio de administración Mensajería instantánea, reuniones \> \> y conferencias. Active las comunicaciones externas. El conmutador de comunicaciones externas activa la conectividad de Skype y las comunicaciones con otras organizaciones que usan Skype Empresarial.
  
Para obtener más información acerca de la administración de Skype Empresarial Online, consulte:
  
- [Permitir a los usuarios contactar con usuarios externos de Skype Empresarial](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [What to try if you can't IM Skype for Business or Skype external contacts](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [Agregar un contacto en Skype Empresarial](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [Administradores: configurar Skype Empresarial para usuarios individuales](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>Implementación de la conectividad de Skype para Skype Empresarial Server

Skype Empresarial Server usa la arquitectura de acceso de federación para admitir la conectividad con Skype. Esta conectividad permite a los usuarios de Skype Empresarial Server agregar Skype. Los clientes de Skype también pueden agregar usuarios de Skype Empresarial a su lista de contactos. En función de las directivas establecidas administrativamente en Skype Empresarial Server, los usuarios podrán comunicarse mediante mensajería instantánea, ver la presencia de los demás e iniciar llamadas de audio y vídeo. La conectividad de Skype también es una característica de Skype Empresarial Online y se puede habilitar para los clientes de Skype Empresarial Online desde el Centro de administración de Skype Empresarial en el Centro de administración de Microsoft 365.
  
> [!NOTE]
> Si Skype Empresarial Server ya está configurado para conectarse con Windows Messenger mediante la Conectividad de mensajería instantánea pública (PIC), la implementación ya está configurada para la conectividad de Skype. El único cambio que puede considerar es cambiar el nombre de la entrada PIC existente de Messenger como Skype. 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>El sitio de aprovisionamiento de conectividad de mensajería instantánea pública de Skype Empresarial Server ya no está disponible

El sitio que anteriormente se usaba para aprovisionar manualmente la federación entre las implementaciones locales de Skype Empresarial y Skype ya no es necesario y se cerrará el 15/8/2019. La federación con Skype ahora usa la detección de socios federados, que es el mismo mecanismo necesario para la federación con Skype Empresarial Online.

La comunicación entre cualquier implementación local de Skype Empresarial y los usuarios de Skype a través de la infraestructura de mensajería instantánea pública existente ahora requiere que la configuración del servidor perimetral local sea compatible con Skype Empresarial Online.

> [!NOTE]
> La mayoría de los clientes no necesitan ninguna acción, incluidas todas las implementaciones federadas con Skype Empresarial Online.
  
Las implementaciones locales deben publicar un registro SRV de DNS de federación para cada dominio que hospedan. La guía está disponible en la [planeación de DNS.](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning) Cada dominio debe resolverse mediante una consulta SRV de DNS en un FQDN del servidor perimetral que satisfaga una coincidencia de sufijo de nivel superior del dominio. Por ejemplo, considere el dominio "contoso.com":

|**FQDN válidos**|**Comentario**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |En cada caso, el FQDN exacto debe estar presente en el SN o en el SAN del certificado externo instalado en el servidor perimetral.   |
|access.contoso.com   ||
|**FQDN no válidos**|**Motivo**|
|sip.contoso-edge.com   |No es una coincidencia de sufijos.  |
|sip.it.contoso.com   |No es una coincidencia de sufijos de nivel superior.   |

Puede encontrar más instrucciones sobre certificados externos en la planeación [de certificados.](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning)

#### <a name="faqs"></a>Preguntas frecuentes

**¿Por qué se está apagando el sitio web de aprovisionamiento?**
El mecanismo de aprovisionamiento de mensajería instantánea pública (PIC) (pic.lync.com) que se implementó en 2006 ya no se puede usar y se cerrará el 15/8/2019. En su lugar, la federación de mensajería instantánea pública asumirá el mismo modelo de federación usado por Skype Empresarial Online, conocido como "detección de partners", por el que una implementación local es detectada públicamente por sus registros SRV de DNS de federación.

**¿Este cambio significa que la federación de mensajería instantánea pública está en desuso?**
No. La federación de mensajería instantánea pública seguirá recibiendo soporte durante muchos años, probablemente hasta que el producto local de Skype Empresarial llegue al final de su vida útil.

**Nuestra empresa tiene una relación híbrida (espacio de direcciones compartido) con Skype Empresarial Online, ¿nos vemos afectados?**
No, dado que ya está federando con Skype Empresarial Online, este cambio no le afectará.
 
**¿Este cambio significa que nuestra empresa tiene que habilitar la federación con Skype Empresarial Online?**
No. Si la configuración del proxy del servidor perimetral no habilita la federación con el proveedor de hospedaje de Skype Empresarial Online (sipfed.online.lync.com), este cambio no afectará a eso. Sin embargo, los mismos requisitos de DNS y certificado que se aplican a la federación con Skype Empresarial Online ahora también se aplican a la federación con usuarios de Skype.
 
**Nuestra empresa es grande y no puede cambiar su configuración perimetral por motivos normativos/de cumplimiento,etc.... ¿Qué podemos hacer?**
Cualquier organización local que no pueda cambiar su configuración de servidor perimetral según se especifique, debe contactar con el soporte técnico del producto lo antes posible.

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>Habilitación de federación y conectividad de mensajería instantánea pública (PIC)

Ahora céntrate en el entorno de Skype Empresarial Server y en las tareas administrativas necesarias para configurar la conectividad de Skype. En esta sección, se supone que el administrador ha implementado Skype Empresarial Server y configurado el acceso externo, también conocido como servidores perimetrales. 
  
Hay tres pasos principales necesarios para habilitar la federación y la PIC. Son:
  
1. Configurar federación y PIC
    
2. Configurar al menos una directiva para admitir el acceso de usuarios federados
    
3. Configurar la configuración del proveedor pic de Skype
    
#### <a name="1-configure-federation-and-pic"></a>1. Configurar federación y PIC

La federación es necesaria para permitir que los usuarios de Skype se comuniquen con los usuarios de Skype Empresarial de su organización. La conectividad de mensajería instantánea (PIC) pública es una clase de federación y debe configurarse para permitir que los usuarios de Skype Empresarial se comuniquen con los usuarios de Skype. La federación y la PIC se configuran mediante el Panel de control de Skype Empresarial Server.
  
> [!NOTE]
> La federación PIC ya no es compatible con las versiones de producto anteriores a Lync Server 2010 (Live Communication Server, Office Communications Server). Las plataformas compatibles con la federación PIC incluyen Skype Empresarial Server, Lync Server 2013 y Lync Server 2010. 
  
La federación es necesaria para permitir que los usuarios de Skype se comuniquen con los usuarios de Skype Empresarial de su organización. La conectividad de mensajería instantánea pública (PIC) es una clase de federación y debe configurarse para permitir que los usuarios de Skype Empresarial Server se comuniquen con los usuarios de Skype. La federación y la PIC se configuran mediante el cuadro de diálogo de configuración perimetral del Panel de control de Skype Empresarial Server, como se muestra en la figura.
  
![Definir nuevo grupo de servidores perimetrales](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> Los atributos EnableSkypeIdRouting y EnableSkypeDirectorySearch deben establecerse en true en la configuración del proveedor público (vea las instrucciones posteriores) para que la búsqueda funcione. 
  
Esto completa las tareas administrativas que deben realizarse en el servidor. Ya está configurado para la conectividad de Skype.
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. Configurar al menos una directiva para admitir el acceso de usuarios federados

Con el Panel de control de Skype Empresarial Server, un administrador debe configurar una o más directivas de acceso de usuarios externos para controlar si los usuarios de Skype pueden colaborar con usuarios internos de Skype Empresarial Server.
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. Configurar la configuración del proveedor pic de Skype

Con el Shell de administración de Skype Empresarial Server, un administrador debe configurar la directiva de cliente de Skype Empresarial para mostrar Skype como un proveedor pic adicional. 
  
> [!NOTE]
> Los usuarios de los proveedores de servicios de conectividad de mensajería instantánea pública (PIC) no pueden participar en mensajería instantánea o conferencias en su organización hasta que también configure al menos una directiva (paso 2, anterior en este procedimiento) para admitir la conectividad de mensajería instantánea pública. 
  
Para las nuevas instalaciones, puede configurar la conectividad de Skype habilitando un proveedor público de Skype mediante el Panel de control de Skype Empresarial Server, como se muestra en la figura.
  
![Proveedores federados SIP](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> Para configurar la conectividad de Skype al actualizar a Skype Empresarial Server, debe quitar y volver a agregar el proveedor público de Skype existente. 
  
La configuración de la conectividad de Skype también se puede realizar solo con PowerShell. Para configurar la conectividad de Skype con PowerShell:
  
1. Desde un servidor front-end de Skype Empresarial Server, abra el Shell de administración de Skype Empresarial Server.
    
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
    
   - ProxyFqdn: ubicación del perímetro de federación de Skype (propiedad/mantenida por Microsoft)
    
   - IconURL: icono usado por el cliente de Lync Skype Empresarial para identificar &amp; visualmente los contactos de Skype
    
   - NameDecorationRoutingDomain y NameDecorationExcludedDomainList: al establecer estas opciones, los usuarios pueden escribir las MSA de los usuarios de Skype sin necesidad de saber cómo "decorar" dominios que no son de Microsoft con "msn.com". Esto elimina la necesidad de escribir "user(contoso.com)@msn.com" para todos los dominios que NO están en ExcludedDomainList. El cliente de SfB dará formato automáticamente a la MSA si el dominio NO está en la lista de excluidos. Hemos agregado los dominios de cuenta de Microsoft más comunes a la lista excluida.
    
     > [!NOTE]
     > El proveedor público debe quitarse y agregarse nuevo si se realizan cambios. No se permiten cambios en la configuración local. 
  
     > [!NOTE]
     > Agregado en el cliente de escritorio Lync CU5 de Lync de Lync &amp; 2013 en Office 2013 SP1, NameDecorationRoutingDomain y NameDecorationExcludedDomainList mejoran la situación en la que los usuarios de Lync que agregan contactos de Skype necesitan "decorar" dominios que no son de Microsoft para identificarlos y enrutrlos a Skype (el formato de: user(contoso.com)@msn.com). Esta nueva configuración permitirá el formato automático de la dirección que escriba el usuario en el cuadro de diálogo "Agregar contacto de Skype" con NameDecorationRoutingDomain (que debe establecerse en msn.com) si no contiene los dominios en NameDecorationExcludedDomainList (actualmente podemos admitir msn.com, live.com, Hotmail.com, outlook.com). 
  
3. Desde un cliente de Skype Empresarial, los usuarios ahora pueden buscar y agregar un usuario de Skype.
    
## <a name="clients-and-interoperability-matrix"></a>Clientes y matriz de interoperabilidad

En la tabla siguiente se describe el estado de interoperabilidad entre la versión más reciente del consumidor de Skype y la versión más reciente de Skype Empresarial.
  

|**Clientes de Skype**|**Agregar contactos, mensajería instantánea, presencia, audio y videollamadas**|**Comentario**|
|:-----|:-----|:-----|
|Escritorio de Skype Windows  <br/> |7.6 o superior, Windows XP y superior  <br/> |**NUEVO:** compatibilidad agregada para el cliente de Skype de Windows que se ejecuta en Windows XP y Windows Vista (requiere la última versión de cliente **7.26 o posterior)** <br/> |
|Skype Mobile: teléfono y tableta Android  <br/> |6.19 o superior, con sistema operativo Android versión 4.0.3 o posterior  <br/> |Es posible que los dispositivos de especificación baja no admitan videollamadas  <br/> |
|Skype Mobile: iOS  <br/> |6.11 o superior, en IOS 7 o superior  <br/> |No se admiten iPhone 4 y versiones anteriores, iPod de 4ª generación y versiones anteriores, iPad de primera generación  <br/> |
|Skype Mac  <br/> |7.19 o superior, en Mac OS X 10.9 (Dallass) o superior  <br/> |Requiere Mac OSX 10.9 o superior  <br/> |
|Skype Universal Windows App (Windows 10) Desktop and Mobile  <br/> |Windows 10 (actualización redstone 1 o posterior)  <br/> |Windows Universal App will receive update in Fall 2016 adding interop support  <br/> |
   
En la tabla siguiente se describe el estado de interoperabilidad entre la versión más reciente de Skype Empresarial y la versión más reciente del consumidor de Skype. 
  
|**Cliente**|**Búsqueda en el directorio de Skype y agregar contactos**|**Skype A/V, interoperabilidad de mensajería instantánea**|
|:-----|:-----|:-----|
|Skype for Business  <br/> |Sí  <br/> |Sí  <br/> |
|Skype Empresarial en Mac  <br/> |Puede agregar (sin búsqueda)  <br/> |Sí  <br/> |
|Lync Desktop 2013  <br/> |Puede agregar (sin búsqueda)  <br/> |Sí  <br/> |
|Lync Web App: en línea y local  <br/> |N/D  <br/> |N/D  <br/> |
|Lync Mobile: Windows Phone  <br/> |Próximamente.  <br/> |Sí  <br/> |
|Lync Mobile- Android  <br/> |Próximamente.  <br/> |Sí  <br/> |
|Lync Mobile: iOS  <br/> |Próximamente.  <br/> |Sí  <br/> |
|Sistema Lync Room  <br/> |Próximamente.  <br/> |Sí  <br/> |
|Lync Modern App (Win 8.1)  <br/> |Sí  <br/> |Sí  <br/> |
|Lync Mac 2011  <br/> |Puede agregar (sin búsqueda)  <br/> |Sí  <br/> |
|Lync Desktop 2010  <br/> |Puede agregar (sin búsqueda)  <br/> |Sí  <br/> |
|Lync Phone Edition  <br/> |N/D  <br/> |N/D  <br/> |
|Lync Attendant  <br/> |N/D  <br/> |N/D  <br/> |
   
