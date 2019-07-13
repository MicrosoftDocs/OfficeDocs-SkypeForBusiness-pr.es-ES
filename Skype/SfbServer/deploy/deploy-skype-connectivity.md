---
title: Implementar conectividad de Skype en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 'Resumen: Aprenda a conectar Skype empresarial Server con el consumidor de Skype. También se conoce como conectividad de Skype.'
ms.openlocfilehash: eae06688e06f143011d4bd6559d6bcbb7b9b61aa
ms.sourcegitcommit: baa425d7a07429e6fe84b4f27c76243cf755c1a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2019
ms.locfileid: "35643181"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>Implementar conectividad de Skype en Skype empresarial Server

**Resumen:** Aprenda a conectar Skype empresarial Server con el consumidor de Skype. También se conoce como conectividad de Skype.
  
Este artículo es una guía para la implementación de la Conectividad de Skype.
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Información general sobre la Conectividad de Skype para profesionales de TI

La conectividad de Skype ofrece a los usuarios de Skype empresarial la posibilidad de buscar y agregar usuarios de Skype. La conectividad de Skype es una característica de Skype para empresas que te permite habilitar la Federación y la búsqueda de directorios con usuarios de Skype. Después de habilitar la conectividad de Skype, los usuarios de Skype empresarial podrán buscar y agregar usuarios de Skype.
  
## <a name="skype-directory-search"></a>Búsqueda en el directorio de Skype

La función Búsqueda en el directorio de Skype ofrece a los usuarios de Skype Empresarial la posibilidad de buscar contactos de Skype. Esta función de búsqueda permite que los usuarios busquen a través de los siguientes filtros:
  
- **Buscar por nombre para mostrar, ejemplo "Juan Pérez"** : esto podría devolver muchos resultados, por lo que es posible que no encuentre lo que está buscando.
    
- **Buscar por nombre para mostrar y ubicación, ejemplo "Juan Pérez en Barcelona"** : Esto reduce considerablemente los resultados de la búsqueda.
    
- **Buscar por correo electrónico, ejemplo "JohnDoe@outlook.com"** -esto debería devolver un resultado en la mayoría de los casos; el que coincide exactamente con el correo electrónico especificado. Pero, si el mismo correo electrónico está asociado con más de una cuenta, puede que esta búsqueda brinde varios resultados.
    
- **Buscar por número de teléfono, ejemplo "123-123-1234"** : esto debería devolver un resultado en la mayoría de los casos; el que coincide exactamente con el teléfono especificado. Es preciso que el número de teléfono incluya el código de país (es decir, 1-xxx-yyy-zzzz). Si el mismo número de teléfono está asociado con más de una cuenta, puede que esta búsqueda brinde varios resultados.
    
- **Buscar por nombre de usuario, ejemplo "JohnDoe1456"** : si se encuentra una coincidencia exacta, se devolverá como el primer resultado. Se pueden devolver otras coincidencias de "nombre" posibles.
    
    > [!NOTE]
    > La búsqueda en el directorio de Skype necesita comunicarse con las siguientes direcciones IP en el puerto 443: 104.40.75.246, 23.101.135.34 y 40.113.86.19. 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Matriz de implementación admitida para la Búsqueda en el directorio de Skype

En la siguiente tabla se resume la compatibilidad para la Búsqueda en el directorio de Skype.
  

||**Front-end de Skype empresarial Server**|**Front-end de Lync Server 2013 (o anterior)**|**Comentarios**|
|:-----|:-----|:-----|:-----|
|Edge de Skype empresarial Server  <br/> |Compatible  <br/> |No compatible  <br/> |Skype empresarial Server y Edge son requisitos previos para la búsqueda en el directorio de Skype  <br/> |
|Borde de Skype empresarial Server Edge + Lync Server 2013 en paralelo  <br/> |Compatible  <br/> |No compatible  <br/> |El tráfico de la Búsqueda en el directorio de Skype fluye por medio de los servidores perimetrales de Skype Empresarial Server. El tráfico de federación lo hace por medio del perímetro configurado por el administrador. Por ejemplo, el administrador puede escoger continuar enviando el tráfico de federación por medio de los servidores perimetrales de Lync Server 2013, que no son compatibles con la Búsqueda en el directorio de Skype.  <br/> |
|Perímetro de Lync Server 2013 (o anterior)  <br/> |No compatible  <br/> |No compatible  <br/> ||
   
> [!NOTE]
> Servicio de la AddressBook que se ejecuta en Skype empresarial Server front end encuentra el límite en la existencia del puerto 4443 de búsqueda de Skype en el servidor EDGE. 
  
> [!NOTE]
> En caso de que un cliente tenga varios sitios en su implementación local y haya implementado solo un servidor o agrupación perimetral de Skype empresarial Server, entonces buscar el tráfico de todos los sitios pasará por el único servidor perimetral disponible. El administrador debe asegurarse de que las agrupaciones de todos los sitios tengan acceso al servidor o grupo de servidores perimetrales de Skype empresarial implementado. 
  
> [!NOTE]
> El servicio gráfico de Skype limitará las solicitudes de búsqueda de todos los clientes locales o de Office 365 si la tasa de solicitudes es mayor que 15 solicitudes por segundo. 
  
> [!NOTE]
> Para clientes locales de grandes empresas, los dominios tendrán que estar permitidos con el servicio de búsqueda de Skype a fin de admitir tasas de solicitudes de mayor tamaño. 
  
> [!NOTE]
> Skype empresarial Server limitará las solicitudes entrantes si hay demasiadas solicitudes pendientes en la cola. 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online-in-office-365"></a>Implementar la Conectividad de Skype para Skype Empresarial Online en Office 365

La Conectividad de Skype es una característica de Skype Empresarial Online, parte de Office 365. Puede activarla desde el Centro de administración de Skype Empresarial en el portal de Office 365.
  
Para Office 365 mediana empresa, Office 365 Enterprise, Office 365 educación y Office 365 para administración pública: inicie sesión en el portal de Office 365 y vaya al centro de administración de Skype empresarial. Vaya a comunicaciones externas. En proveedores de servicios de mensajería instantánea pública, haga clic en habilitar. Si desea controlar el acceso de usuarios individuales a la conectividad de Skype, puede hacerlo modificando la configuración de comunicaciones externas de cada usuario.
  
Para Office 365 pequeña empresa Premium: inicie sesión en Office 365 y vaya a configuración \> \> del servicio de administración mensajería instantánea, reuniones y conferencias. Activar las comunicaciones externas. El interruptor de comunicaciones externas activa tanto la conectividad de Skype como las comunicaciones con otras organizaciones que usan Skype empresarial.
  
Para más información sobre la administración de Skype Empresarial Online, consulte:
  
- [Permitir a los usuarios contactar con usuarios externos de Skype Empresarial](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [Qué puede probar si no puede enviar mensajería instantánea a contactos externos de Skype empresarial o Skype](https://support.office.com/en-us/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [Agregar un contacto en Skype empresarial](https://support.office.com/en-US/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [Administradores: Configurar Skype Empresarial para usuarios individuales](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>Implementación de conectividad de Skype para Skype empresarial Server

Skype empresarial Server usa la arquitectura de acceso a la Federación para admitir conectividad con Skype. Esta conectividad habilita a los usuarios de Skype Empresarial Server a agregar Skype. Los clientes de Skype también pueden agregar usuarios de Skype Empresarial a la lista de contactos. En función de las directivas establecidas administrativamente en Skype empresarial Server, los usuarios podrán comunicarse con la mensajería instantánea, ver la presencia de los demás e iniciar llamadas de audio y vídeo. Asimismo, la Conectividad de Skype es una característica de Skype Empresarial Online y puede habilitarse para los clientes de Skype Empresarial Online desde el Centro de administración de Skype Empresarial en el portal de Office 365.
  
> [!NOTE]
> Si Skype Empresarial Server ya se encuentra configurado con Windows Messenger por medio de Public Instant Messaging Connectivity (PIC), su implementación ya se encuentra configurada para la Conectividad de Skype. Posiblemente, el único cambio que desee realizar será cambiar el nombre de la entrada PIC de Messenger existente a Skype.  
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>El sitio de aprovisionamiento de la conectividad de mensajería instantánea pública de Skype empresarial Server ya no está disponible

El sitio que anteriormente se usaba para aprovisionar manualmente la Federación entre las implementaciones locales de Skype para empresas y Skype ya no es necesario y se cerrará el 8/15/2019. La Federación con Skype ahora usa el descubrimiento de socios federados, que es el mismo mecanismo necesario para la Federación con Skype empresarial online.

La comunicación entre cualquier implementación local de Skype empresarial y los usuarios de Skype a través de la infraestructura pública de mensajería instantánea existente requiere ahora que la configuración del servidor perimetral local sea compatible con Skype empresarial online.

> [!NOTE]
> La mayoría de los clientes no necesita ninguna acción, incluidas todas las implementaciones que se federan con Skype empresarial online.
  
Es necesario que las implementaciones locales publiquen un registro SRV de DNS de Federación para cada dominio que hospedan. La guía está disponible en el [planeamiento de DNS](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning). Cada dominio debe resolverse mediante una consulta SRV de DNS a un FQDN de servidor perimetral que satisfaga una coincidencia de sufijo de nivel superior del dominio. Por ejemplo, considere el dominio "contoso.com":

|**FQDN válidos**|**Comentario**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |En cada caso, el FQDN exacto debe estar presente en el SN o en la SAN del certificado externo instalado en el servidor perimetral.   |
|access.contoso.com   ||
|**FQDN no válidos**|**Motivo**|
|sip.contoso-edge.com   |No es una coincidencia de sufijo.  |
|sip.it.contoso.com   |No coincide un sufijo de nivel superior.   |

Puede encontrar más información sobre los certificados externos en el [planeamiento de certificados](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning).

#### <a name="faqs"></a>Preguntas frecuentes

**¿Por qué se cierra el sitio web de aprovisionamiento?**
El mecanismo de aprovisionamiento de la mensajería instantánea pública (PIC) que se implementó en 2006 ya no se puede usar y se cerrará en 8/15/2019. En su lugar, la Federación de la mensajería instantánea pública asumirá el mismo modelo de Federación que usa Skype empresarial online, conocido como "descubrimiento del asociado", mediante el cual una implementación local puede ser detectada públicamente por su Federación de registros SRV de DNS.

**¿Este cambio significa que la Federación pública de mensajería instantánea está en desuso?**
No. La Federación de mensajería instantánea pública seguirá siendo admitida durante muchos años, probablemente hasta que el producto local de Skype empresarial llegue al final de la vida.

**Nuestra empresa tiene una relación híbrida (espacio de direcciones compartidas) con Skype empresarial online, ¿estamos afectados?**
No, puesto que ya está en la Federación con Skype empresarial online, este cambio no le afectará.
 
**¿Este cambio significa que nuestra empresa tiene que habilitar la Federación con Skype empresarial online?**
No. Si la configuración del proxy del servidor perimetral no permite la Federación con el proveedor de hospedaje de Skype empresarial online (sipfed.online.lync.com), este cambio no afectará. Sin embargo, los mismos requisitos de DNS y certificados que se aplican a la Federación con Skype empresarial online también se aplican a la Federación con usuarios de Skype.
 
**Nuestra empresa es grande y no puede cambiar su configuración de la periferia debido a motivos normativos, de cumplimiento y etc... ¿Qué podemos hacer?**
Cualquier organización local que no pueda cambiar la configuración del servidor perimetral según lo especificado debe ponerse en contacto con el servicio de asistencia al producto lo antes posible.

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>Habilitar la federación y la conectividad de mensajería instantánea pública (PIC)

Ahora céntrese en el entorno de Skype empresarial Server y en las tareas administrativas necesarias para configurar la conectividad de Skype. En esta sección, se asume que el administrador ya ha implementado Skype Empresarial Server y configurado el acceso externo, conocido también como servidores perimetrales. 
  
La habilitación de la federación y la PIC consta de tres pasos principales, que son:
  
1. Configurar la federación y la PIC
    
2. Configurar al menos una directiva para permitir el acceso de usuarios federados
    
3. Configurar las opciones del proveedor de la PIC para Skype
    
#### <a name="1-configure-federation-and-pic"></a>1. Configurar la federación y la PIC

La federación es necesaria para permitir que los usuarios de Skype se comuniquen con los usuarios de Skype Empresarial de la organización. Es preciso configurar Public Instant Messaging Connectivity (PIC), que es un tipo de federación, para que los usuarios de Skype Empresarial se puedan comunicar con los usuarios de Skype. La federación y la PIC se configuran por medio del Panel de control de Skype Empresarial Server.
  
> [!NOTE]
> La Federación de PIC ya no es compatible con las versiones de producto anteriores a Lync Server 2010 (Live Communication Server, Office Communications Server). Las plataformas compatibles con la Federación de PIC incluyen Skype empresarial Server, Lync Server 2013 y Lync Server 2010. 
  
La federación es necesaria para permitir que los usuarios de Skype se comuniquen con los usuarios de Skype Empresarial de la organización. Es preciso configurar Public Instant Messaging Connectivity (PIC), que es un tipo de federación, para que los usuarios de Skype Empresarial Server se puedan comunicar con los usuarios de Skype. La federación y la PIC se configuran por medio del diálogo Configuración perimetral del Panel de control de Skype Empresarial Server, como se muestra en la figura.
  
![Definir un nuevo grupo de servidores perimetrales](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> En la configuración del proveedor público, es necesario establecer los atributos EnableSkypeIdRouting y EnableSkypeDirectorySearch en True (consulte las instrucciones a continuación) para que funcione la búsqueda. 
  
Estas son todas las tareas administrativas que se necesitan llevar a cabo en el servidor. Ahora ya está todo configurado para la Conectividad de Skype.
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. configurar al menos una directiva para que sea compatible con el acceso de usuarios federados

Es preciso que un administrador configure una o varias directivas de acceso de usuarios externos desde el Panel de control de Skype Empresarial Server para controlar si los usuarios de Skype pueden colaborar con usuarios internos de Skype Empresarial Server.
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. configurar la opción de proveedor de PIC de Skype

En el Shell de administración de Skype Empresarial Server, es preciso que un administrador configure la directiva de cliente de Skype Empresarial para mostrar Skype como un proveedor de PIC adicional.  
  
> [!NOTE]
> Los usuarios de los proveedores de servicios de conectividad de mensajería instantánea pública (PIC) no pueden participar en mensajes instantáneos o conferencias de su organización hasta que también configure al menos una directiva (paso 2, anteriormente en este procedimiento) para admitir la conectividad de mensajería instantánea pública. 
  
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
    
   - IconURL: icono usado por el &amp; cliente de Skype empresarial de Lync para identificar visualmente los contactos de Skype
    
   - NameDecorationRoutingDomain y NameDecorationExcludedDomainList: la configuración permite a los usuarios introducir el servicio MSAs de los usuarios de Skype sin necesidad de saber "decorar" Dominios que no son de Microsoft con "msn.com". Esto elimina la necesidad de escribir "User (contoso. com) @msn. com" para todos los dominios que no están en la ExcludedDomainList. El cliente SfB convertirá el formato de MSA automáticamente si el dominio NO se encuentra en la lista de dominios excluidos. Hemos agregado los dominios de la cuenta de Microsoft más comunes a la lista de excluidos.
    
     > [!NOTE]
     > Si se realizan cambios en el proveedor público, es preciso quitarlo y agregarlo de nuevo. No se permiten cambios locales. 
  
     > [!NOTE]
     > Agregado en el cliente de escritorio &amp; de lync Server 2013 CU5 en el SP1 de Office 2013, la NameDecorationRoutingDomain y NameDecorationExcludedDomainList mejoran la situación en la que los usuarios de Lync que agregan contactos de Skype necesitan "decorar" Dominios que no son de Microsoft para identificar y enrutarlos a Skype (el formato de: usuario (contoso. com) @msn. com). Esta nueva configuración permitirá el formato automático de la dirección de entrada del usuario en el cuadro de diálogo "agregar contacto de Skype" con el NameDecorationRoutingDomain (que debe establecerse en msn.com) si no contiene los dominios de la NameDecorationExcludedDomainList ( Actualmente podemos admitir msn.com, live.com, Hotmail.com, outlook.com). 
  
3. Desde un cliente de Skype Empresarial, los usuarios ahora pueden buscar y agregar un usuario de Skype.
    
## <a name="clients-and-interoperability-matrix"></a>Matriz de interoperabilidad y clientes

La tabla siguiente detalla el estado de la interoperabilidad entre la última versión de consumidor de Skype y la última versión de Skype Empresarial.
  

|**Clientes de Skype**|**Agregar contactos, MI, presencia, llamadas de audio y vídeo**|**Comentario**|
|:-----|:-----|:-----|
|Skype para escritorio de Windows  <br/> |7.6 o superior, Windows XP o superior  <br/> |**Nuevo**: soporte técnico agregado para el cliente de Skype de Windows en Windows XP y Windows Vista **(requiere la versión más reciente de cliente 7,26 o superior)** <br/> |
|Skype móvil: teléfonos y tabletas Android   <br/> |6.19 o superior, ejecutando la versión de SO Android 4.0.3 o superior  <br/> |Es posible que los dispositivos con especificaciones inferiores no admitan videollamadas  <br/> |
|Skype Mobile-iOS  <br/> |6.11 o superior, en iOS 7 o superior  <br/> |Los dispositivos iPhone 4 y iPod de 4.ª generación o anteriores y iPad de 1.ª generación no son compatibles  <br/> |
|Skype Mac  <br/> |7.19 o superior, en Mac OSX 10.9 (Mavericks) o superior  <br/> |Requiere Mac OS X 10.9 o superior  <br/> |
|Aplicación de Windows universal de Skype (Windows 10) para escritorios y móviles  <br/> |Windows 10 (actualización Redstone 1 o superior)  <br/> |La aplicación universal de Windows se actualizará en el otoño de 2016 para agregarle compatibilidad con interoperabilidad  <br/> |
   
La tabla siguiente detalla el estado de la interoperabilidad entre la última versión de Skype Empresarial y la última versión de Skype para consumidores.  
  
|**Cliente**|**Agregar contactos y búsqueda en el directorio de Skype**|**Audio o vídeo de Skype, interoperabilidad de mensajería instantánea**|
|:-----|:-----|:-----|
|Skype Empresarial  <br/> |Sí  <br/> |Sí  <br/> |
|Skype Empresarial en Mac  <br/> |Puede agregar (no buscar)  <br/> |Sí  <br/> |
|Lync Desktop 2013  <br/> |Puede agregar (no buscar)  <br/> |Sí  <br/> |
|Lync Web App: local y en línea  <br/> |N/D  <br/> |N/D  <br/> |
|Lync Mobile: Windows Phone  <br/> |Próximamente  <br/> |Sí  <br/> |
|Lync Mobile: Android  <br/> |Próximamente  <br/> |Sí  <br/> |
|Lync Mobile: iOS  <br/> |Próximamente  <br/> |Sí  <br/> |
|Sistema Lync Room  <br/> |Próximamente  <br/> |Sí  <br/> |
|Lync Modern App (Win 8.1)  <br/> |Sí  <br/> |Sí  <br/> |
|Lync Mac 2011  <br/> |Puede agregar (no buscar)  <br/> |Sí  <br/> |
|Lync Desktop 2010  <br/> |Puede agregar (no buscar)  <br/> |Sí  <br/> |
|Lync Phone Edition  <br/> |N/D  <br/> |N/D  <br/> |
|Lync Attendant  <br/> |N/D  <br/> |N/D  <br/> |
   

