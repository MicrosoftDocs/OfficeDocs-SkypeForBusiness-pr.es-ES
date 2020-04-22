---
title: Implementar la conectividad de Skype en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 'Resumen: Obtenga información sobre cómo conectar Skype empresarial Server con consumidores de Skype. También se conoce como conectividad de Skype.'
ms.openlocfilehash: 2cf124c340218a352f55fa1c09302a0d0f1d972a
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780069"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>Implementar la conectividad de Skype en Skype empresarial Server

**Resumen:** Obtenga información sobre cómo conectar Skype empresarial Server con consumidor de Skype. También se conoce como conectividad de Skype.
  
En este artículo se explica cómo implementar la conectividad de Skype.
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Información general sobre la conectividad de Skype para profesionales de ti

La conectividad de Skype proporciona a los usuarios de Skype empresarial la capacidad de buscar y agregar usuarios de Skype. La conectividad de Skype es una característica de Skype empresarial que permite habilitar la búsqueda de Federación y directorios con usuarios de Skype. Después de habilitar la conectividad de Skype, los usuarios de Skype empresarial podrán buscar y agregar usuarios de Skype.
  
## <a name="skype-directory-search"></a>Búsqueda en el directorio de Skype

La funcionalidad de búsqueda en el directorio de Skype ofrece a los usuarios de Skype empresarial la capacidad de buscar contactos de Skype. La funcionalidad de búsqueda permite a los usuarios realizar búsquedas mediante lo siguiente:
  
- **Buscar por nombre para mostrar, ejemplo "John Doe"** : esto podría devolver muchos resultados, por lo que es posible que no encuentre lo que busca.
    
- **Buscar por nombre para mostrar y ubicación, ejemplo "Juan Pérez en Barcelona"** : esto reducirá considerablemente los resultados de la búsqueda.
    
- **Buscar por correo electrónico, ejemplo "JohnDoe@outlook.com"** : esto debe devolver un resultado en la mayoría de los casos; el que coincide exactamente con el correo electrónico especificado. Pero si el mismo correo electrónico está asociado con más de una cuenta, se pueden devolver varios resultados.
    
- **Buscar por número de teléfono, ejemplo "123-123-1234"** : esto debe devolver un resultado en la mayoría de los casos; el que coincide exactamente con el teléfono especificado. El número de teléfono debe incluir el código de país (por ejemplo, 1-xxx-yyy-ZZZZ). Si el mismo número de teléfono está asociado a más de una cuenta, puede que se devuelvan varios resultados.
    
- **Buscar por nombre de Skype, ejemplo "JohnDoe1456"** : si se encuentra una coincidencia exacta, se devolverá como el primer resultado. Es posible que se devuelvan otras coincidencias de "nombre".
    
    > [!NOTE]
    > La búsqueda en el directorio de Skype debe ser capaz de comunicarse con las siguientes direcciones IP en el puerto 443:104.40.75.246, 23.101.135.34 y 40.113.86.19. 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Matriz de implementación admitida para la búsqueda en el directorio de Skype

En la tabla siguiente se describe la compatibilidad con la búsqueda en el directorio de Skype.
  

||**Front-end de Skype empresarial Server**|**Lync Server 2013 (o anterior) front-end**|**Comments**|
|:-----|:-----|:-----|:-----|
|Servidor perimetral de Skype empresarial Server  <br/> |Compatible  <br/> |No compatible  <br/> |Skype empresarial Server y el servidor perimetral son requisitos previos para la búsqueda en el directorio de Skype  <br/> |
|Servidor perimetral de Skype empresarial Server + servidor perimetral de Lync Server 2013 en paralelo  <br/> |Compatible  <br/> |No compatible  <br/> |El tráfico de búsqueda en el directorio de Skype fluye a través de servidores perimetrales de Skype empresarial Server. El tráfico de la Federación pasa por el servidor perimetral configurado por el administrador. Por ejemplo, el administrador puede elegir continuar enviando tráfico de Federación a través de servidores perimetrales de Lync Server 2013, que no admitirá la búsqueda en el directorio de Skype.  <br/> |
|Servidor perimetral de Lync Server 2013 (o anterior)  <br/> |No se admite  <br/> |No se admite  <br/> ||
   
> [!NOTE]
> El servicio de la AddressBook que se ejecuta en el front-end de Skype empresarial Server encuentra el perímetro por la existencia del puerto de búsqueda de Skype 4443 en el servidor perimetral. 
  
> [!NOTE]
> En caso de que un cliente tenga varios sitios en su implementación local y haya implementado un solo servidor o grupo perimetral de Skype empresarial Server, la búsqueda de tráfico de todos los sitios pasará por el servidor perimetral disponible. El administrador debe asegurarse de que los grupos de servidores de todos los sitios puedan acceder al servidor o grupo de servidores perimetrales de Skype empresarial Server implementado. 
  
> [!NOTE]
> El servicio de gráfico de Skype limitará las solicitudes de búsqueda de todos los clientes locales o de Microsoft 365 u Office 365 si la tasa de solicitudes supera las 15 solicitudes/segundo. 
  
> [!NOTE]
> En el caso de los clientes locales de grandes empresas, los dominios tendrán que estar en la lista blanca con el servicio de búsqueda de Skype para permitir una mayor tasa de solicitudes. 
  
> [!NOTE]
> Skype empresarial Server limitará las solicitudes entrantes si hay demasiadas solicitudes pendientes en la cola. 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online-in-office-365"></a>Implementación de conectividad de Skype para Skype empresarial online en Office 365

La conectividad de Skype también es una característica de Skype empresarial online, que forma parte de Office 365. Puede habilitar la característica conectividad de Skype desde el centro de administración de Skype empresarial en el centro de administración de Microsoft 365.
  
Para Office 365 mediana empresa, Office 365 Enterprise, Office 365 Education y Office 365 para administración pública: inicie sesión en el centro de administración de Microsoft 365 y vaya al centro de administración de Skype empresarial. Vaya a comunicaciones externas. En proveedores de servicios de mensajería instantánea pública, haga clic en habilitar. Si desea controlar el acceso de usuarios individuales a la conectividad de Skype, puede hacerlo si modifica la configuración de las comunicaciones externas de los usuarios individuales.
  
Para Office 365 Small Business Premium: inicie sesión en Office 365 y vaya a configuración \> \> del servicio de administración mensajería instantánea, reuniones y conferencias. Active las comunicaciones externas. El conmutador de comunicaciones externas activa tanto la conectividad de Skype como las comunicaciones con otras organizaciones que usan Skype empresarial.
  
Para obtener más información acerca de la administración de Skype empresarial online, consulte:
  
- [Permitir a los usuarios contactar con usuarios externos de Skype Empresarial](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [Qué puede probar si no puede enviar mensajería instantánea a contactos externos de Skype empresarial o Skype](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [Agregar un contacto en Skype empresarial](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [Administradores: configurar Skype empresarial para usuarios individuales](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>Implementación de la conectividad de Skype para Skype empresarial Server

Skype empresarial Server usa la arquitectura de acceso a la Federación para admitir la conectividad con Skype. Esta conectividad permite a los usuarios de Skype empresarial Server agregar Skype. Los clientes de Skype también pueden agregar usuarios de Skype empresarial a su lista de contactos. En función de las directivas establecidas de forma administrativa en Skype empresarial Server, los usuarios podrán comunicarse mediante la mensajería instantánea, ver la presencia de los demás e iniciar llamadas de audio y vídeo. La conectividad de Skype también es una característica de Skype empresarial online y puede habilitarse para los clientes de Skype empresarial online desde el centro de administración de Skype empresarial en el centro de administración de Microsoft 365.
  
> [!NOTE]
> Si Skype empresarial Server ya está configurado para conectarse con Windows Messenger mediante Public Instant Messaging Connectivity (PIC), la implementación ya está configurada para la conectividad de Skype. El único cambio que debería considerar es cambiar el nombre de la entrada de PIC de Messenger existente como Skype. 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>El sitio de aprovisionamiento de conectividad de mensajería instantánea pública de Skype empresarial Server ya no está disponible

El sitio que anteriormente se usaba para aprovisionar manualmente la Federación entre las implementaciones locales de Skype empresarial y Skype ya no es necesario y se apagará el 8/15/2019. La Federación con Skype ahora usa el descubrimiento de socios federados, que es el mismo mecanismo necesario para la Federación con Skype empresarial online.

La comunicación entre cualquier implementación local de Skype empresarial y los usuarios de Skype a través de la infraestructura de mensajería instantánea pública actual requiere ahora la configuración del servidor perimetral local para que sea compatible con Skype empresarial online.

> [!NOTE]
> La mayoría de los clientes no necesitan ninguna acción, incluidas todas las implementaciones que se federan con Skype empresarial online.
  
Las implementaciones locales son necesarias para publicar un registro SRV de DNS de Federación para cada dominio que hospedan. La guía está disponible en la [planeación de DNS](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning). Cada dominio debe resolverse mediante una consulta SRV de DNS a un FQDN de servidor perimetral que satisfaga una coincidencia de sufijo de nivel superior del dominio. Por ejemplo, considere el dominio "contoso.com":

|**FQDN válidos**|**Comment**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |En cada caso, el FQDN exacto debe estar presente en el SN o en el SAN del certificado externo instalado en el servidor perimetral.   |
|access.contoso.com   ||
|**FQDN no válidos**|**Motivo**|
|sip.contoso-edge.com   |No es una coincidencia de sufijo.  |
|sip.it.contoso.com   |No es una coincidencia de sufijo de nivel superior.   |

Puede encontrar más información sobre los certificados externos en la [planeación de certificados](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning).

#### <a name="faqs"></a>Preguntas frecuentes

**¿Por qué se apaga el sitio web de aprovisionamiento?**
El mecanismo de aprovisionamiento de mensajería instantánea pública (PIC) (pic.lync.com) que se implementó en 2006 ya no se puede atender y se cerrará en 8/15/2019. En su lugar, la Federación de mensajería instantánea pública asumirá el mismo modelo de Federación que usa Skype empresarial online, conocido como "detección de asociados", mediante el cual una implementación local es reconocible públicamente por sus registros SRV de DNS de Federación.

**¿Este cambio significa que la Federación de mensajería instantánea pública está en desuso?**
No. La Federación de mensajería instantánea pública seguirá siendo compatible durante muchos años, probablemente hasta que el producto local de Skype empresarial llegue al final de la vida útil.

**Nuestra compañía tiene una relación híbrida (espacio de direcciones compartido) con Skype empresarial online, ¿estamos afectados?**
No, como ya se ha Federo con Skype empresarial online, este cambio no le afectará.
 
**¿Este cambio significa que nuestra compañía tiene que habilitar la Federación con Skype empresarial online?**
No. Si la configuración de proxy del servidor perimetral no permite la Federación con el proveedor de hospedaje de Skype empresarial online (sipfed.online.lync.com), este cambio no afectará a eso. Sin embargo, los mismos requisitos de certificado y DNS que se aplican a la Federación con Skype empresarial online también se aplican a la Federación con usuarios de Skype.
 
**Nuestra compañía es grande y no puede cambiar su configuración de la periferia debido a motivos normativos, de cumplimiento, etc. ¿Qué se puede hacer?**
Cualquier organización local que no pueda cambiar la configuración del servidor perimetral según lo especificado debe llegar a soporte técnico del producto lo antes posible.

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>Habilitación de la Federación y la conectividad de mensajería instantánea pública (PIC)

Ahora céntrese en el entorno de Skype empresarial Server y en las tareas administrativas necesarias para configurar la conectividad de Skype. En esta sección, se supone que el administrador ha implementado Skype empresarial Server y configurado el acceso externo, también conocido como servidores perimetrales. 
  
Se requieren tres pasos principales para habilitar la Federación y PIC. Son:
  
1. Configurar la Federación y el PIC
    
2. Configurar al menos una directiva para admitir el acceso de usuarios federados
    
3. Configurar el valor del proveedor de PIC de Skype
    
#### <a name="1-configure-federation-and-pic"></a>1. configurar la Federación y el PIC

La Federación es necesaria para permitir que los usuarios de Skype se comuniquen con los usuarios de Skype empresarial de su organización. Public Instant Messaging Connectivity (PIC) es una clase de Federación y debe configurarse para permitir que los usuarios de Skype empresarial se comuniquen con los usuarios de Skype. La Federación y el PIC se configuran mediante el panel de control de Skype empresarial Server.
  
> [!NOTE]
> La Federación de PIC ya no es compatible con las versiones de producto anteriores a Lync Server 2010 (Live Communication Server, Office Communications Server). Las plataformas compatibles para la Federación de PIC incluyen Skype empresarial Server, Lync Server 2013 y Lync Server 2010. 
  
La Federación es necesaria para permitir que los usuarios de Skype se comuniquen con los usuarios de Skype empresarial de su organización. Public Instant Messaging Connectivity (PIC) es una clase de Federación y debe configurarse para permitir que los usuarios de Skype empresarial Server se comuniquen con los usuarios de Skype. La Federación y el PIC se configuran mediante el cuadro de diálogo Configuración perimetral del panel de control de Skype empresarial Server, tal como se muestra en la figura.
  
![Definir nuevo grupo de servidores perimetrales](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> Los atributos EnableSkypeIdRouting y EnableSkypeDirectorySearch deben establecerse en true en la configuración del proveedor público (consulte las instrucciones más adelante) para que funcione la búsqueda. 
  
Esto completa las tareas administrativas que deben realizarse en el servidor. Ya está configurado para la conectividad de Skype.
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. configurar al menos una directiva para que admita el acceso de usuarios federados

Mediante el panel de control de Skype empresarial Server, un administrador debe configurar una o más directivas de acceso de usuarios externos para controlar si los usuarios de Skype pueden colaborar con los usuarios de Skype empresarial Server internos.
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. configurar la configuración del proveedor de PIC de Skype

Mediante el shell de administración de Skype empresarial Server, un administrador debe configurar la Directiva de cliente de Skype empresarial para mostrar Skype como un proveedor de PIC adicional. 
  
> [!NOTE]
> Los usuarios de los proveedores de servicios de conectividad de mensajería instantánea pública (PIC) no pueden participar en mensajería instantánea o conferencias en su organización hasta que también configure al menos una directiva (paso 2, anteriormente en este procedimiento) para que admita la conectividad de mensajería instantánea pública. 
  
Para las instalaciones nuevas, puede configurar la conectividad de Skype si habilita un proveedor público de Skype mediante el panel de control de Skype empresarial Server, como se muestra en la figura.
  
![Proveedores federados SIP](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> Para configurar la conectividad de Skype al actualizar a Skype empresarial Server, debe quitar y volver a agregar el proveedor público de Skype existente. 
  
La configuración de la conectividad de Skype también puede realizarse con PowerShell. Para configurar la conectividad de Skype con PowerShell:
  
1. En un servidor front-end de Skype empresarial Server, abra el shell de administración de Skype empresarial Server.
    
2. Ejecute los dos comandos siguientes:
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > Si todavía no tiene un proveedor PIC en el entorno y está creando un nuevo proveedor PIC, no es necesario que ejecute el cmdlet Remove-CsPublicProvider. 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    ¿Qué hacen los parámetros menos obvios?
    
   - ProxyFqdn: ubicación de la Federación de Skype perimetral (propiedad o mantenida por Microsoft)
    
   - IconURL: icono usado por el &amp; cliente de Skype empresarial Lync para identificar visualmente los contactos de Skype
    
   - NameDecorationRoutingDomain y NameDecorationExcludedDomainList: la configuración permite a los usuarios escribir el "MSAs" de los usuarios de Skype sin tener que saber "msn.com" de los dominios que no son de Microsoft. Esto elimina la necesidad de escribir "User (contoso. com) @msn. com" para todos los dominios que no se encuentran en ExcludedDomainList. Si el dominio no está en la lista de exclusión, el cliente de SfB formateará automáticamente la MSA. Hemos agregado los dominios de cuentas de Microsoft más comunes a la lista de excluidos.
    
     > [!NOTE]
     > El proveedor público debe quitarse y agregarse New si se realizan cambios. No se permiten los cambios locales. 
  
     > [!NOTE]
     > Agregado en Lync Server 2013 CU5 &amp; Lync Desktop Client en Office 2013 SP1, NameDecorationRoutingDomain y NameDecorationExcludedDomainList mejoran la situación en la que los usuarios de Lync que agregan contactos de Skype necesitan "decorar" Dominios que no son de Microsoft para identificarlos y enrutarlos a Skype (el formato de: User (contoso. com) @msn. com). Esta nueva configuración permitirá el formato automático de la dirección del usuario en el cuadro de diálogo "agregar contacto de Skype" con la NameDecorationRoutingDomain (que debe establecerse en msn.com) si no contiene los dominios de NameDecorationExcludedDomainList (actualmente, admite msn.com, live.com, Hotmail.com, outlook.com). 
  
3. Desde un cliente de Skype empresarial, los usuarios ahora pueden buscar y agregar un usuario de Skype.
    
## <a name="clients-and-interoperability-matrix"></a>Matriz de clientes e interoperabilidad

En la tabla siguiente se describe el estado de la interoperabilidad entre la última versión de Skype Consumer y la última versión de Skype empresarial.
  

|**Clientes de Skype**|**Agregar contactos, la mensajería instantánea, la presencia, el audio y las llamadas de vídeo**|**Comment**|
|:-----|:-----|:-----|
|Escritorio de Windows Skype  <br/> |7,6 o superior, Windows XP y posterior  <br/> |**Nuevo**: compatibilidad agregada para el cliente de Skype para Windows que se ejecuta en Windows XP y Windows Vista **(requiere la versión más reciente del cliente 7,26 o posterior)** <br/> |
|Skype móvil: teléfonos y tabletas Android  <br/> |6,19 o superior, ejecutar Android OS versión 4.0.3 o posterior  <br/> |Es posible que los dispositivos de especificación baja no admitan llamadas de vídeo  <br/> |
|Skype móvil-iOS  <br/> |6,11 o superior, en IOS 7 o superior  <br/> |No es compatible con iPhone 4 y anteriores, iPod 4th Generation y anteriores, iPad 1st Generation  <br/> |
|Mac de Skype  <br/> |7,19 o superior, en Mac OS X 10,9 (Mavericks) o superior  <br/> |Requiere Mac OSX 10,9 o superior  <br/> |
|Equipos de escritorio y móviles de aplicaciones de Windows universales de Skype (Windows 10)  <br/> |Windows 10 (Redstone 1 actualización o posterior)  <br/> |La aplicación universal de Windows recibirá la actualización en caída 2016 adición de compatibilidad con interoperabilidad  <br/> |
   
En la tabla siguiente se describe el estado de la interoperabilidad entre la última versión de Skype empresarial y la versión más reciente del consumidor de Skype. 
  
|**Cliente**|**Búsqueda en el directorio de Skype y agregar contactos**|**Skype A/V, interoperabilidad de mensajería instantánea**|
|:-----|:-----|:-----|
|Skype for Business  <br/> |Sí  <br/> |Sí  <br/> |
|Skype Empresarial en Mac  <br/> |Puede Agregar (sin búsqueda)  <br/> |Sí  <br/> |
|Lync Desktop 2013  <br/> |Puede Agregar (sin búsqueda)  <br/> |Sí  <br/> |
|Lync Web App-en línea y local  <br/> |N/D  <br/> |N/D  <br/> |
|Lync Mobile-Windows Phone  <br/> |Próximamente.  <br/> |Sí  <br/> |
|Lync Mobile-Android  <br/> |Próximamente.  <br/> |Sí  <br/> |
|Lync Mobile: iOS  <br/> |Próximamente.  <br/> |Sí  <br/> |
|Sistema Lync Room  <br/> |Próximamente.  <br/> |Sí  <br/> |
|Aplicación moderna de Lync (Win 8,1)  <br/> |Sí  <br/> |Sí  <br/> |
|Lync Mac 2011  <br/> |Puede Agregar (sin búsqueda)  <br/> |Sí  <br/> |
|Lync Desktop 2010  <br/> |Puede Agregar (sin búsqueda)  <br/> |Sí  <br/> |
|Lync Phone Edition  <br/> |N/D  <br/> |N/D  <br/> |
|Operador de Lync  <br/> |N/D  <br/> |N/D  <br/> |
   

