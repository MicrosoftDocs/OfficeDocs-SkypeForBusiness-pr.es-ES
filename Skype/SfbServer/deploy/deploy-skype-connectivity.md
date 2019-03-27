---
title: Implementación de la conectividad de Skype en Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 'Resumen: Descubra cómo conectar Skype para Business Server con Skype consumidor. También conocido como la conectividad de Skype.'
ms.openlocfilehash: 3dd48661b230f4e780505be4aeb05bbe9ff82340
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874510"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>Implementación de la conectividad de Skype en Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo conectar Skype para Business Server con Skype consumidor. También conocido como la conectividad de Skype.
  
Este artículo es una guía para la implementación de la Conectividad de Skype.
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Información general sobre la Conectividad de Skype para profesionales de TI

Conectividad de Skype proporciona Skype para los usuarios de negocios con la capacidad de buscar y agregar usuarios de Skype. Conectividad de Skype es una característica de Skype para la empresa que le permite habilitar la búsqueda de Active Directory y la federación con los usuarios de Skype. Después de habilitar la conectividad de Skype su Skype para usuarios profesionales podrán buscar y agregar usuarios de Skype.
  
## <a name="skype-directory-search"></a>Búsqueda en el directorio de Skype

La función Búsqueda en el directorio de Skype ofrece a los usuarios de Skype Empresarial la posibilidad de buscar contactos de Skype. Esta función de búsqueda permite que los usuarios busquen a través de los siguientes filtros:
  
- **Buscar por nombre para mostrar, en el ejemplo se "Arturo López"** - Esto podría devolver el número de resultados, por lo que no pueden encontrar lo está buscando.
    
- **Búsqueda por nombre para mostrar más ubicación, ejemplo "John Doe en Barcelona"** - esto va a restringir los resultados de la búsqueda considerablemente.
    
- **Buscar por correo electrónico, en el ejemplo se "johndoe@outlook.com"** - esto debe devolver un resultado en la mayoría de los casos; la única que coincide exactamente con el correo electrónico especificada. Pero, si el mismo correo electrónico está asociado con más de una cuenta, puede que esta búsqueda brinde varios resultados.
    
- **Buscar por número de teléfono, en el ejemplo se "123-123-1234"** - esto debe devolver un resultado en la mayoría de los casos; la única que coincide exactamente con el teléfono especificado. Es preciso que el número de teléfono incluya el código de país (es decir, 1-xxx-yyy-zzzz). Si el mismo número de teléfono está asociado con más de una cuenta, puede que esta búsqueda brinde varios resultados.
    
- **Buscar por nombre de Skype, ejemplo "JohnDoe1456"** - si se encuentra una coincidencia exacta, se devuelve como el resultado de la primera. Otras posibles coincidencias "nombre" es posible que se devolverá.
    
    > [!NOTE]
    > La búsqueda en el directorio de Skype necesita comunicarse con las siguientes direcciones IP en el puerto 443: 104.40.75.246, 23.101.135.34 y 40.113.86.19. 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Matriz de implementación admitida para la Búsqueda en el directorio de Skype

En la siguiente tabla se resume la compatibilidad para la Búsqueda en el directorio de Skype.
  

||**Skype para profesionales de servidor Front-End**|**Front-end de Lync Server 2013 (o anterior)**|**Comentarios**|
|:-----|:-----|:-----|:-----|
|Skype para servidor perimetral de negocio  <br/> |Compatible  <br/> |No compatible  <br/> |Skype para Business Server y perimetral son requisitos previos para la búsqueda de Active Directory de Skype  <br/> |
|Skype para servidor perimetral de negocio + servidor perimetral de Lync Server 2013 implementada en paralelo  <br/> |Compatible  <br/> |No compatible  <br/> |El tráfico de la Búsqueda en el directorio de Skype fluye por medio de los servidores perimetrales de Skype Empresarial Server. El tráfico de federación lo hace por medio del perímetro configurado por el administrador. Por ejemplo, el administrador puede escoger continuar enviando el tráfico de federación por medio de los servidores perimetrales de Lync Server 2013, que no son compatibles con la Búsqueda en el directorio de Skype.  <br/> |
|Perímetro de Lync Server 2013 (o anterior)  <br/> |No compatible  <br/> |No compatible  <br/> ||
   
> [!NOTE]
> Servicio de libreta de direcciones que se ejecuta en Skype para profesionales de servidor Front-End busca el borde por la existencia del puerto 4443 de búsqueda de Skype en el servidor perimetral. 
  
> [!NOTE]
> En caso de que un cliente tiene varios sitios en su implementación local, y si ha implementado un solo Skype para profesionales servidor perimetral o grupo de servidores, a continuación, buscar el tráfico de todos los sitios se vaya a través del único servidor perimetral disponible. El administrador debe asegurarse de que los grupos de servidores de todos los sitios pueden tener acceso a la Skype implementado para profesionales servidor perimetral o grupo de servidores. 
  
> [!NOTE]
> El servicio gráfico de Skype limitará las solicitudes de búsqueda de todos los clientes locales o de Office 365 si la tasa de solicitudes es mayor que 15 solicitudes por segundo. 
  
> [!NOTE]
> Para clientes locales de grandes empresas, los dominios tendrán que estar permitidos con el servicio de búsqueda de Skype a fin de admitir tasas de solicitudes de mayor tamaño. 
  
> [!NOTE]
> Skype para Business Server va a limitar las solicitudes entrantes, si hay demasiadas solicitudes pendientes en la cola. 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online-in-office-365"></a>Implementar la Conectividad de Skype para Skype Empresarial Online en Office 365

La Conectividad de Skype es una característica de Skype Empresarial Online, parte de Office 365. Puede activarla desde el Centro de administración de Skype Empresarial en el portal de Office 365.
  
Para Office 365 mediana empresa, Office 365 Enterprise, Education de Office 365 y Office 365 para el gobierno: iniciar sesión en Office 365 portal y navegue hasta el Skype para el centro de administración de negocio. Vaya a comunicaciones externas. Proveedores de servicios de mensajería instantánea pública, haga clic en habilitar. Si desea controlar el acceso de usuarios individuales a la conectividad de Skype, puede hacerlo mediante la edición de la configuración de comunicaciones externas de los usuarios individuales.
  
Para Office 365 Small Business Premium: Inicie sesión en Office 365 y vaya a administrador \> configuración del servicio \> reuniones de mensajes, instantáneas y conferencias. Activar comunicaciones externas. El modificador de comunicaciones externas activa la conectividad de Skype y la comunicación con otras organizaciones que utilizan Skype para la empresa.
  
Para más información sobre la administración de Skype Empresarial Online, consulte:
  
- [Permitir a los usuarios contactar con usuarios externos de Skype Empresarial](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [¿Qué debe intentar si no puede Skype de mensajería instantánea para contactos externos empresariales o de Skype](https://support.office.com/en-us/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [Agregar un contacto en Skype para la empresa](https://support.office.com/en-US/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [Administradores: Configurar Skype Empresarial para usuarios individuales](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>Implementación de la conectividad de Skype para Skype para Business Server

Skype para Business Server usa la arquitectura de acceso de federación para admitir la conectividad con Skype. Esta conectividad habilita a los usuarios de Skype Empresarial Server a agregar Skype. Los clientes de Skype también pueden agregar usuarios de Skype Empresarial a la lista de contactos. En función de las directivas de forma administrativa establecidas en Skype para Business Server, los usuarios podrán comunicarse mediante mensajería instantánea, consulte la presencia del otro e iniciar llamadas de audio y vídeos. Asimismo, la Conectividad de Skype es una característica de Skype Empresarial Online y puede habilitarse para los clientes de Skype Empresarial Online desde el Centro de administración de Skype Empresarial en el portal de Office 365.
  
> [!NOTE]
> Si Skype Empresarial Server ya se encuentra configurado con Windows Messenger por medio de Public Instant Messaging Connectivity (PIC), su implementación ya se encuentra configurada para la Conectividad de Skype. Posiblemente, el único cambio que desee realizar será cambiar el nombre de la entrada PIC de Messenger existente a Skype.  
  
### <a name="accessing-the-skype-for-business-server-public-im-connectivity-provisioning-site-from-skype-for-business-server"></a>Obtener acceso a la Skype para sitio aprovisionamiento de Business Server public IM connectivity de Skype para Business Server

Este proceso de aprovisionamiento puede tardar hasta treinta días en completarse, aunque posiblemente demore solo unos días según la cantidad de solicitudes. Recomendamos que inicie este proceso antes de continuar con el resto de los pasos que aparecen en este documento. Una vez terminado el proceso de aprovisionamiento de Skype para su cuenta, esta se activará y los usuarios válidos se habilitarán para la conectividad de mensajería instantánea pública.  
  
Para aprovisionar la Conectividad de Skype, necesita la siguiente información:
  
- Número del contrato de Microsoft
    
- Nombre de dominio completo (FQDN) del servicio perimetral de acceso
    
- Dominio(s) del Protocolo de inicio de sesión (SIP)
    
- Todos los FQDN del servicio perimetral de acceso adicionales
    
- Información de contacto
    
Para iniciar el proceso de aprovisionamiento para la Conectividad de Skype:
  
1. Inicie sesión en el sitio Web, https://pic.lync.com, utilizando su cuenta de Microsoft Windows Live ID.
    
2. Seleccione el tipo de contrato de licencia de Microsoft.
    
3. Active la casilla para confirmar que ha leído y acepta los derechos de uso del producto de Skype Empresarial Server.
    
4. En la página Iniciar una solicitud de aprovisionamiento, haga clic en el vínculo correspondiente para iniciar una solicitud de aprovisionamiento:
    
5. En la página Especificar la información de aprovisionamiento, escriba el FQDN del servicio perimetral de acceso. Por ejemplo, sip.contoso.com.
    
    > [!IMPORTANT]
    > A partir del 1 de julio de 2017 Microsoft solicitará adicionalmente a los clientes que tengan el registro SRV de DNS de federación implementado para que la conectividad de mensajería instantánea pública siga funcionando.  
  
6. Escriba uno o varios nombres de dominio SIP y, luego, haga clic en Agregar.
    
    > [!NOTE]
    > Se necesita por lo menos un servidor perimetral de acceso para completar el proceso de aprovisionamiento. Mientras un FQDN del servidor perimetral de acceso puede admitir varios dominios SIP, un único dominio SIP no se puede representar por más de un FQDN del servidor perimetral de acceso. El dominio SIP y el servidor perimetral de acceso necesitan estar activos, funcionar y ser accesibles en la red.              
  
7. En la lista de Proveedores de servicios públicos de MI, seleccione Skype y haga clic en Siguiente para agregar la información de contacto y enviar la solicitud de aprovisionamiento.
    
Una vez enviada la solicitud de aprovisionamiento, pueden pasar hasta 30 días hasta que se active la cuenta y se habilite a los usuarios para la Conectividad de Skype, aunque puede demorar solo unos días según la cola.
  
### <a name="enabling-federation-and-public-im-connectivity-pic"></a>Habilitar la federación y la conectividad de mensajería instantánea pública (PIC)

Una vez que haya enviado la solicitud de aprovisionamiento, puede concentrarse en las tareas administrativas y del entorno de Skype Empresarial Server necesarias para configurar la Conectividad de Skype. En esta sección, se asume que el administrador ya ha implementado Skype Empresarial Server y configurado el acceso externo, conocido también como servidores perimetrales.  
  
La habilitación de la federación y la PIC consta de tres pasos principales, que son:
  
1. Configurar la federación y la PIC
    
2. Configurar al menos una directiva para permitir el acceso de usuarios federados
    
3. Configurar las opciones del proveedor de la PIC para Skype
    
#### <a name="1-configure-federation-and-pic"></a>1. Configurar la federación y la PIC

La federación es necesaria para permitir que los usuarios de Skype se comuniquen con los usuarios de Skype Empresarial de la organización. Es preciso configurar Public Instant Messaging Connectivity (PIC), que es un tipo de federación, para que los usuarios de Skype Empresarial se puedan comunicar con los usuarios de Skype. La federación y la PIC se configuran por medio del Panel de control de Skype Empresarial Server.
  
> [!NOTE]
> La federación de PIC ya no es compatible con Live Communication Server 2005 SP1 ni con Office Communications Server 2007. Las plataformas compatibles para la federación de mensajería instantánea pública incluyen Skype para Business Server, Lync Server 2013, Lync Server 2010 y Office Communications Server 2007 R2. 
  
La federación es necesaria para permitir que los usuarios de Skype se comuniquen con los usuarios de Skype Empresarial de la organización. Es preciso configurar Public Instant Messaging Connectivity (PIC), que es un tipo de federación, para que los usuarios de Skype Empresarial Server se puedan comunicar con los usuarios de Skype. La federación y la PIC se configuran por medio del diálogo Configuración perimetral del Panel de control de Skype Empresarial Server, como se muestra en la figura.
  
![Definir un nuevo grupo de servidores perimetrales](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> En la configuración del proveedor público, es necesario establecer los atributos EnableSkypeIdRouting y EnableSkypeDirectorySearch en True (consulte las instrucciones a continuación) para que funcione la búsqueda. 
  
Estas son todas las tareas administrativas que se necesitan llevar a cabo en el servidor. Ahora ya está todo configurado para la Conectividad de Skype.
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. configurar al menos una directiva para admitir el acceso de usuarios federados

Es preciso que un administrador configure una o varias directivas de acceso de usuarios externos desde el Panel de control de Skype Empresarial Server para controlar si los usuarios de Skype pueden colaborar con usuarios internos de Skype Empresarial Server.
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. configurar el proveedor de mensajería instantánea pública de Skype configuración

En el Shell de administración de Skype Empresarial Server, es preciso que un administrador configure la directiva de cliente de Skype Empresarial para mostrar Skype como un proveedor de PIC adicional.  
  
> [!NOTE]
> Los usuarios de los proveedores de servicios públicos instantánea mensajería conectividad (PIC) no pueden participar en conferencias en su organización o de mensajería instantánea hasta que también configurar al menos una directiva (paso 2, anteriormente en este procedimiento) para admitir la conectividad de mensajería instantánea pública. 
  
Para las nuevas instalaciones, puede configurar la Conectividad de Skype al habilitar un proveedor público de Skype por medio del Panel de control de Skype Empresarial Server, como se muestra en la figura.
  
![Proveedores de SIP federados](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> Es necesario quitar y volver a agregar el proveedor público de Skype existente para configurar la Conectividad de Skype al actualizar Skype Empresarial Server. 
  
También puede configurar la Conectividad de Skype solo con PowerShell. Para hacerlo solo con PowerShell:
  
1. Desde un servidor front-end de Skype Empresarial Server, abra el Shell de administración de Skype Empresarial Server.
    
2. Ejecute estos dos comandos:
    
   ```
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > Si aún no cuenta con ningún proveedor de PIC en el entorno y está creando un proveedor de PIC, no es necesario ejecutar el cmdlet Remove-CsPublicProvider.  
  
   ```
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    ¿Cuál es la función de los parámetros que no son tan fáciles de interpretar?
    
   - ProxyFqdn: ubicación del perímetro de federación de Skype (propiedad de Microsoft o bajo su mantenimiento)
    
   - IconURL: icono Lync usado &amp; Skype para clientes empresariales identificar visualmente los contactos de Skype
    
   - NameDecorationRoutingDomain y NameDecorationExcludedDomainList: establecer estas permite que los usuarios escriban MSAs los usuarios de Skype sin necesidad de conocer "decorar" dominios que no son de Microsoft con "msn.com". Esto elimina la necesidad de escribir "usuario (contoso.com) @msn.com" para todos los dominios que no están en la ExcludedDomainList. El cliente SfB convertirá el formato de MSA automáticamente si el dominio NO se encuentra en la lista de dominios excluidos. Hemos agregado los dominios más comunes de Microsoft Account a la lista de exclusión.
    
     > [!NOTE]
     > Si se realizan cambios en el proveedor público, es preciso quitarlo y agregarlo de nuevo. No se permiten cambios locales. 
  
     > [!NOTE]
     > Agregado en Lync Server 2013 CU5 &amp; la situación donde los usuarios de Lync agregar contactos de Skype necesarios para "decorar" dominios que no son de Microsoft para mejorar el cliente de escritorio de Lync en Office 2013 SP1, NameDecorationRoutingDomain y NameDecorationExcludedDomainList identificar y enrutará a Skype (el formato de: user(contoso.com)@msn.com). Le permitirá estas nuevas opciones de formato automático de la dirección del usuario de escribir en el cuadro de diálogo "Agregar contacto de Skype" con el NameDecorationRoutingDomain (que debe establecerse en msn.com) si no contiene los dominios en el (NameDecorationExcludedDomainList que actualmente podemos admitir msn.com, live.com, Hotmail.com, outlook.com). 
  
3. Desde un cliente de Skype Empresarial, los usuarios ahora pueden buscar y agregar un usuario de Skype.
    
## <a name="clients-and-interoperability-matrix"></a>Matriz de interoperabilidad y clientes

La tabla siguiente detalla el estado de la interoperabilidad entre la última versión de consumidor de Skype y la última versión de Skype Empresarial.
  

|**Clientes de Skype**|**Agregar contactos, MI, presencia, llamadas de audio y vídeo**|**Comentario**|
|:-----|:-----|:-----|
|Skype para escritorio de Windows  <br/> |7.6 o superior, Windows XP o superior  <br/> |**NEW**: se ha agregado compatibilidad con para cliente de Skype de Windows que se ejecutan en Windows XP y Windows Vista **(requiere la versión más reciente de cliente 7.26 o superior)** <br/> |
|Skype móvil: teléfonos y tabletas Android   <br/> |6.19 o superior, ejecutando la versión de SO Android 4.0.3 o superior  <br/> |Es posible que los dispositivos con especificaciones inferiores no admitan videollamadas  <br/> |
|Skype Mobile - iOS  <br/> |6.11 o superior, en iOS 7 o superior  <br/> |Los dispositivos iPhone 4 y iPod de 4.ª generación o anteriores y iPad de 1.ª generación no son compatibles  <br/> |
|Skype Mac  <br/> |7.19 o superior, en Mac OSX 10.9 (Mavericks) o superior  <br/> |Requiere Mac OS X 10.9 o superior  <br/> |
|Aplicación de Windows universal de Skype (Windows 10) para escritorios y móviles  <br/> |Windows 10 (actualización Redstone 1 o superior)  <br/> |La aplicación universal de Windows se actualizará en el otoño de 2016 para agregarle compatibilidad con interoperabilidad  <br/> |
   
La tabla siguiente detalla el estado de la interoperabilidad entre la última versión de Skype Empresarial y la última versión de Skype para consumidores.  
  
|**Cliente**|**Agregar contactos y búsqueda en el directorio de Skype**|**Audio o vídeo de Skype, interoperabilidad de mensajería instantánea**|
|:-----|:-----|:-----|
|Skype Empresarial  <br/> |Sí   <br/> |Sí   <br/> |
|Skype Empresarial en Mac  <br/> |Puede agregar (no buscar)  <br/> |Sí  <br/> |
|Lync Desktop 2013  <br/> |Puede agregar (no buscar)  <br/> |Sí  <br/> |
|Lync Web App: local y en línea  <br/> |N/D  <br/> |N/D  <br/> |
|Lync Mobile: Windows Phone  <br/> |Próximamente  <br/> |Sí  <br/> |
|Lync Mobile: Android  <br/> |Próximamente  <br/> |Sí  <br/> |
|Lync Mobile: iOS  <br/> |Próximamente  <br/> |Sí  <br/> |
|Sistema Lync Room  <br/> |Próximamente  <br/> |Sí  <br/> |
|Lync Modern App (Win 8.1)  <br/> |Sí  <br/> |Sí   <br/> |
|Lync Mac 2011  <br/> |Puede agregar (no buscar)  <br/> |Sí  <br/> |
|Lync Desktop 2010  <br/> |Puede agregar (no buscar)  <br/> |Sí  <br/> |
|Lync Phone Edition  <br/> |N/D  <br/> |N/D  <br/> |
|Lync Attendant  <br/> |N/D  <br/> |N/D  <br/> |
   

