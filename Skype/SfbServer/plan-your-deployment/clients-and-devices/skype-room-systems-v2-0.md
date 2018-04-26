---
title: Plan para Sistemas de salas de Skype v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
description: Este artículo explica las consideraciones de planeación relevantes para la implementación de sistemas de salas de Skype v2, la próxima generación de sistemas de salas de Skype.
ms.openlocfilehash: 372c920eaeaaee050e420cd25195565555426561
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="plan-for-skype-room-systems-v2"></a>Plan para Sistemas de salas de Skype v2
 
Este artículo explica las consideraciones de planeación relevantes para la implementación de sistemas de salas de Skype v2, la próxima generación de sistemas de salas de Skype. 
  
 Sistemas de salas de Skype v2 es la más reciente solución de conferencia de Microsoft diseñada para transformar un Skype enriquecido, colaboración de experiencia empresarial en la sala de reunión. Los usuarios disfrutarán de su familiar Skype para la interfaz de negocio y los administradores de TI podrán apreciar una aplicación de Windows 10 Skype reunión implementan y administran con facilidad. Sistemas de salas de Skype v2 está diseñado para aprovechar los equipos existentes como los paneles LCD para la facilidad de instalación para poner Skype para los negocios en la sala de reunión.
  
Sistemas de salas de Skype v2 utiliza una aplicación UWP específica que actúa como la interfaz de usuario de la sesión de Skype. Se ejecuta en un Surface Pro 4 o Surface Pro en un modo de consola (una vez implementada la aplicación UWP es la única aplicación que se ejecuta en el dispositivo) y requiere su propia cuenta de dispositivo en su Skype para la implementación del negocio. Aprovecha el equipo existente, como los paneles LCD y las cámaras y los micrófonos periféricos (que tienen un precio bastante económico), para que la experiencia que se ofrece en la sala de reuniones sea de gran calidad. El software se actualiza a través de la Tienda Windows y de Windows Update.
  
Antes de comenzar a preparar el entorno, asegúrese de tener el software y el hardware necesarios. Para obtener más información, vea [requisitos de los sistemas de salas de Skype v2](requirements.md). 
  
> [!NOTE]
> Sistemas de salas de Skype v2 está destinado para su uso con Skype Business Server 2015 o Skype para los negocios en línea. No se esperan trabajar con sistemas de salas de Skype v2 plataformas anteriores como Lync Server 2013. 
  
Sistemas de salas de Skype v2 es la más reciente solución de conferencia de Microsoft diseñada para transformar un Skype enriquecido, colaboración de experiencia empresarial en la sala de reunión. Los usuarios disfrutarán de su familiar Skype para la interfaz de negocio y los administradores de TI podrán apreciar una aplicación de Windows 10 Skype reunión implementan y administran con facilidad. Sistemas de salas de Skype v2 está diseñado para aprovechar los equipos existentes como los paneles LCD para la facilidad de instalación para poner Skype para los negocios en la sala de reunión.
  
 **Creado para Skype Empresarial**
  
- Un solo toque para unirse a reuniones de Skype.
    
- La experiencia de las reuniones de Skype optimizada para salas con prestaciones de audio HD de banda ancha y vídeo HD en toda la pantalla.
    
- Todos los participantes se pueden conectar a la reunión de Skype mediante el dispositivo que elijan desde el lugar en el que se encuentren.
    
- Invite a las personas desde su directorio, donde podrá consultar su disponibilidad en ese mismo momento o a través de una llamada de teléfono.
    
- Es compatible con los servicios de conferencias RTC y llamadas RTC de Skype Empresarial como sustitución del teléfono de conferencias independiente de su sala.
    
 **Transforme cualquier sala de reuniones**
  
- Una aplicación de reuniones de Skype dedicada y optimizada para el controlador táctil situado en el centro de la mesa y las pantallas frontales de gran tamaño.
    
- Permite aprovechar las inversiones que ya ha realizado en pantallas frontales o proyectores.
    
- Funciona en todo tipo de áreas de reuniones, desde los espacios más apiñados a las salas de conferencias más amplias.
    
- Los dispositivos de audio y vídeo certificados de Skype Empresarial están disponibles para diversos tamaños de salas.
    
- Transmisión por cable integrada para compartir el escritorio del proyecto con la sala y con la reunión de Skype.
    
- Selección de usuario en la aplicación de reunión sala de audio y vídeo dispositivos USB & #x 2776;
    
- Soporte de doble pantalla (para la paridad de sistemas heredados) & #x 2777;
    
- Themability (temas integrados y la capacidad para establecer un tema personalizado) & #x 2777;
    
 **Fácil de implementar, sencillo de administrar.**
  
- Un dispositivo que está encendido en todo momento y que activará automáticamente las pantallas cuando detecte que hay alguna persona en la sala.
    
- Sencilla implementación y actualización de la aplicación de reuniones de Skype para UWP (Plataforma universal de Windows).
    
- Windows AppLocker bloquea el dispositivo con la aplicación de reuniones de Skype.
    
- Se supervisa y se administra como un dispositivo con Windows 10 Enterprise mediante Intune y SCCM (MDM).
    
- Fiabilidad de carácter empresarial.
    
- La formación que requieren los usuarios es muy poca puesto que ya conocen la interfaz de usuario de Skype.
    
- Se ejecuta en tablet Surface Pro 4
    
- Integra la sala consola informes de estado de los clientes que utilicen Microsoft Operations Management Suite (Véase [administración de Plan de sistemas de salas de Skype v2 con OMS](oms-management.md)) & #x 2776;
    
- Capacidad de enviar comentarios para compilaciones públicas & #x 2777;
    
- Unirse a una telemetría mejorada alrededor de reunión confiabilidad & #x 2777;
    
- Otros informes de OMS & #x 2777;
    
- Capacidad de administración de TI para configurar de forma remota dispositivos & #x 2777;
    <!--  - Front-of-Room UX shows room details pre-meeting U2  -->
- Se ejecuta en tablet Surface Pro & #x 2778;
    
- Compatible con Windows 10 Enterprise Creator Update (en inglés, compilación 1703) & #x 2778;
    
- Soporte para [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system) acoplar hardware & #x 2778;
    
- Soporte técnico de OEM para controles del entorno (Crestron) & #x 2778;
    
- Soporte para [La serie Polycom MSR](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl) acoplar hardware & #x 2779;
    
- Soporte para [Logitech Brio](https://www.logitech.com/en-us/product/brio) & #x 2779;

- Soporte de [Lenovo concentrador 500](https://www3.lenovo.com/us/en/hub500) acoplar hardware & #x277A;  
    
& #x 2776; -Característica incluida en la actualización 1 (SW Ver. 2.0.2.0).
  
& #x 2777; -Característica presentada en Update 2 (SW Ver. 3.0.6.0). 
  
& #x 2778; -Característica presentada en actualización 3 (SW Ver. 3.0.12.0). 
  
& #x 2779; -Característica incluida en la actualización 4 (SW Ver. 3.0.15.0). 

& #x277A; -Característica incluida en la actualización 5 (SW Ver. 3.1.98.0). 
  
## <a name="preparing-your-skype-for-business-environment"></a>Preparación del entorno de Skype Empresarial

Esta sección contiene una visión general de los pasos necesarios para preparar el entorno para que puedan utilizar todas las características de los sistemas de salas de Skype v2.
  
1. Prepare una cuenta de dispositivo para cada consola v2 de sistemas de salas de Skype. Para obtener más información, vea [implementar sistemas de salas de Skype v2](../../deploy/deploy-clients/room-systems-v2.md) .
    
2. Asegúrese de que las conexiones de red y de Internet funcionen correctamente en el dispositivo que se va a utilizar.  
    
  - Debe ser capaz de recibir una dirección IP mediante DHCP (Nota: los sistemas de salas de Skype v2 no se puede configurar con una dirección IP estática en el primer inicio de unidad)
    
  - Debe tener estos puertos abiertos (además de abrir los puertos normales para los medios de Skype Empresarial):
    
  - HTTPS: 443
    
  - HTTP: 80
    
  - Si su red se ejecuta mediante un proxy, necesitará también la dirección del proxy o la información de script.
    
    > [!NOTE]
    > Sistemas de salas de Skype v2 no admite entrada HDCP, que se ha observado para causar problemas con HDMI ingieren funcionalidad (vídeo, audio). Tenga cuidado para garantizar que los conmutadores conectados a sistemas de salas de Skype v2 tienen opciones HDCP desactivados. 
  
3. Para poder mejorar su experiencia, Microsoft recopila información. Para recopilar información, necesitamos que estos sitios figuren en la lista de permitidos:
    
  - Extremo de cliente de telemetría:https://vortex.data.microsoft.com/
    
  - Extremo de la configuración de telemetría:https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>Crear y probar una cuenta de dispositivo

Una *cuenta del dispositivo* es una cuenta que utiliza el cliente de v2 de sistemas de salas de Skype para tener acceso a características de Exchange, como el calendario y habilitar Skype para el negocio. Para obtener más información, vea [implementar sistemas de salas de Skype v2](../../deploy/deploy-clients/room-systems-v2.md) .
  
### <a name="check-network-availability"></a>Comprobar la disponibilidad de red

Para que funcione correctamente, el dispositivo de los sistemas de salas de Skype v2 debe tener acceso a una red cableada que cumpla estos requisitos:
  
- Tener acceso a su instancia de Active Directory o Azure Active Directory (Azure AD), así como a sus servidores de Microsoft Exchange y Skype Empresarial.
    
- Tener acceso a un servidor que pueda proporcionar una dirección IP mediante DHCP. Sistemas de salas de Skype v2 no puede configurarse con una dirección IP estática.
    
- Tener acceso a los puertos HTTP 80 y 443.
    
- Puertos TCP y UDP configurados como se describe en los [requisitos de puerto para Lync Server 2013](https://technet.microsoft.com/en-us/library/gg398798%28v=ocs.15%29.aspx) para Premise Skype para implementaciones empresariales o [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) para Skype para implementaciones de negocios en línea.
    
> [!IMPORTANT]
> Asegúrese de usar una conexión de red cableada de 1 Gbps para garantizar que dispondrá de la banda ancha necesaria.  
  
### <a name="certificates"></a>Certificados

El dispositivo de los sistemas de salas de Skype v2 utiliza certificados para servicios Web de Exchange, Skype para el negocio, el uso de la red y la autenticación. En el caso de que los servidores relacionados utilicen certificados públicos, como ocurre con las implementaciones en línea y algunas locales, no será necesario que el administrador realice ninguna otra acción en relación a la instalación de certificados. Si, por el contrario, la entidad de certificación es una CA privada (habitual en las instalaciones locales), el dispositivo necesita poder confiar en esa CA, lo que implica tener los certificados de la cadena CA + CA instalados en el dispositivo. Al añadir el dispositivo al dominio, esta tarea se realiza de forma automática.
  
Los certificados se instalarán del mismo modo en que se instalarían para cualquier otro cliente de Windows.  
  
> [!NOTE]
> Para disponer de sistemas de salas de Skype v2 utiliza Skype para Business Server se requiera certificados. 
  
### <a name="proxy"></a>Proxy

Sistemas de salas de Skype v2 está diseñado para heredar la configuración de Proxy del sistema operativo Windows. Acceda al SO Windows de la siguiente manera:
  
1. En la interfaz de usuario de sistemas de salas de Skype v2, haga clic en el icono del engranaje de configuración donde se le pedirá la contraseña de administrador local en el dispositivo (la contraseña predeterminada es "sfb").
    
2. Puntee en "Configuración" seguida punteando en el botón "Ir a Windows" y, a continuación, en el "obtuvo para inicio de sesión de administrador en" botón y, a continuación, haga clic en el botón de "Administrador" (si el equipo está unido al dominio elegir "Otro usuario", entonces utilice. \admin como nombre de usuario).
    
3. En la "búsqueda de Windows" cuadro inferior izquierdo en regedit (ya sea larga presione la pantalla o a la derecha haga clic en y elija "Ejecutar como administrador").
    
4. Haga clic en la carpeta HKEY_USERS (podrá ver una lista de identificadores de seguridad de los usuarios de la máquina), asegúrese de que la carpeta raíz HKEY_USERS esté seleccionada.
    
    Se le pedirá un nombre de clave para la sección recién cargada; Escriba en Skype (ahora debería ver la configuración del registro para el usuario de Skype).
    
5. Haga clic en Archivo y, a continuación, elija "Cargar subárbol".
    
6. Busque la carpeta "C:\Users\Skype" y, en el cuadro Nombre de archivo, escriba NNTUSER.dat y después presione el botón para abrir.
    
7. Abrir la clave de Skype y vaya a configuración de HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet, a continuación, asegurarse de que estos valores se especifican: 
    
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    
    "MigrateProxy" = dword: 00000001
    
    "ProxyEnable" = dword: 00000001
    
    "ProxyServer"="xx.xx.xx.xx:8080"
    
    Si ProxyServer no existe, es posible que deba agregar esta clave como una cadena, cambie xx.xx.xx.xx:8080 a la dirección IP/host y al puerto de su servidor Proxy.
    
8. Una vez que haya terminado de realizar los cambios que resalte el usuario Skype tecla (en la carpeta raíz de Skype) y elija Descargar sección en el menú archivo de registro (se le pedirá confirmación - seleccionar **Sí** ).
    
9. Ahora puede cerrar el editor del registro y escribir cerrar la sesión en el cuadro de búsqueda de Windows.
    
10. Nuevamente en la pantalla de inicio de sesión, elija el usuario de **Skype**. Si todos los pasos anteriores se realizaron correctamente, el dispositivo de los sistemas de salas de Skype v2 se signo de correctamente.
    
Para usar esta aplicación, debe poder conectarse a los puntos de conexión que se describen a continuación. Para ver las direcciones IP, amplíe la sección de direcciones IP que se encuentra debajo de la tabla que describe el flujo de tráfico.
  
**Ejemplos de servidor de seguridad Proxy Host nombre/puerto**

|**Propósito**|**Origen o credenciales**|**Puerto de origen**|**Destino**|**CDN**|**ExpressRoute para Office 365**|**Destino IP**|**Puerto de destino**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Autenticación e identidad  <br/> |Vea la [identidad y la autenticación de Office 365](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Identity) <br/> |||
|Portal e infraestructura compartida  <br/> |Vea el [Office 365 portal y compartida](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Portal-identity) <br/> |||
|Señalización de SIP  <br/> |Equipo cliente o usuario conectado  <br/> |Puertos efímeros  <br/> |\*. contoso.com  <br/> |No  <br/> |Sí  <br/> |[Skype para rangos de IP de negocios](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Conferencia web de conexiones PSOM (modelo de objetos compartidos persistentes)  <br/> |Equipo cliente o usuario conectado  <br/> |Puertos efímeros  <br/> |\*. contoso.com  <br/> |No  <br/> |Sí  <br/> |[Skype para rangos de IP de negocios](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Descargas HTTPS  <br/> |Equipo cliente o usuario conectado  <br/> |Puertos efímeros  <br/> |\*. contoso.com  <br/> |No  <br/> |Sí  <br/> |[Skype para rangos de IP de negocios](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Audio  <br/> |Equipo cliente o usuario conectado  <br/> |TCP/UDP 50.000-50.019  <br/> |\*. contoso.com  <br/> |No  <br/> |Sí  <br/> |[Skype para rangos de IP de negocios](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, UDP 3478, TCP/UDP 50.000-59.999  <br/> |
|Vídeo  <br/> |Equipo cliente o usuario conectado  <br/> |TCP/UDP 50.020-50.039  <br/> |\*. contoso.com  <br/> |No  <br/> |Sí  <br/> |[Skype para rangos de IP de negocios](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, UDP 3478, TCP/UDP 50.000-59.999  <br/> |
|Compartir escritorio  <br/> |Equipo cliente o usuario conectado  <br/> |TCP/UDP 50.040-50.059  <br/> |\*. contoso.com  <br/> |No  <br/> |Sí  <br/> |[Skype para rangos de IP de negocios](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, 50.000-59.999  <br/> |
|Notificaciones de inserción de Lync Mobile para Lync Mobile 2010 en dispositivos iOS. No es necesario para dispositivos móviles Android, Nokia Symbian o Windows Phone.  <br/> |Equipo cliente o usuario conectado  <br/> |Puertos efímeros  <br/> |\*. contoso.com  <br/> |No  <br/> |Sí  <br/> |[Skype para rangos de IP de negocios](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 5223  <br/> |
|Telemetría de Skype  <br/> |Equipo cliente o usuario conectado  <br/> |Puertos efímeros  <br/> |skypemaprdsitus.trafficmanager.NET  <br/> pipe.Skype.com  <br/> |No  <br/> |No  <br/> |N/D  <br/> |TCP 443  <br/> |
|Sugerencias rápidas del cliente de Skype  <br/> |Equipo cliente o usuario conectado  <br/> |Puertos efímeros  <br/> |quicktips.skypeforbusiness.com  <br/> |No  <br/> |No  <br/> |N/D  <br/> |TCP 443  <br/> |
   
> [!NOTE]
> El carácter comodín de contoso.com y broadcast.skype.com representa una larga lista de nodos que se utilizan en exclusividad para Office 365. 
  
### <a name="create-provisioning-packages"></a>Crear paquetes de aprovisionamiento

Aprovisionamiento de paquetes utilizará para autenticarse en Exchange Server o Skype para Business Server.
  
### <a name="admin-group-management"></a>Administración del grupo de administradores

Después de la unión a un dominio, puede usar la Directiva de grupo o la Administración del equipo local para configurar un Grupo de seguridad como administrador local, tal como lo haría para un PC con Windows en su dominio. Las personas que formen parte de ese grupo de seguridad podrán introducir sus credenciales y desbloquear Configuración.
  
> [!NOTE]
> Si su dispositivo de sistemas de salas de Skype v2 pierde la confianza con el dominio (por ejemplo, si quita la versión 2 de sistemas de salas de Skype desde el dominio después de está unido al dominio), no podrá autenticar en el dispositivo y abra las opciones. La solución alternativa es iniciar sesión con la cuenta de administrador local. 
  
## <a name="local-accounts"></a>Cuentas locales

### <a name="skype-room-systems-local-user-account"></a>Cuenta de usuario local de Sistemas de salas de Skype

Normalmente, la cuenta de dispositivo no requiere una contraseña. Es posible asignarle una, pero acarrea consecuencias, como que los usuarios se puedan quedar bloqueados fuera de la aplicación de consola cuando expire la contraseña. Por lo tanto, el administrador debe garantizar que la contraseña no esté configurada para que expire.
  
### <a name="admin---local-administrator-account"></a>"Administrador": cuenta de administrador local

La contraseña predeterminada de los sistemas de salas de Skype v2 se establece en "sfb". Se puede cambiar la contraseña localmente desde configuración de Windows \> vaya a Windows o en el archivo AutoUnattend.xml (utilice el Administrador de imágenes de sistema de Windows de ADK para realizar el cambio en el archivo xml).
  
> [!CAUTION]
> Asegúrese de cambiar la contraseña de v2 de sistemas de salas de Skype tan pronto como sea posible. 
  
Otra manera de administrar la contraseña de administrador local es configurar una directiva de grupo en la que los administradores de dominio se conviertan en administradores locales.
  
La contraseña del administrador local no se incluye como opción durante la configuración.
  
### <a name="machine-account"></a>Cuenta de equipo

Mucho al igual que cualquier dispositivo de Windows, el nombre del equipo puede cambiar el nombre haciendo clic en configuración de \> sobre \> cambiar el nombre de PC.
  
 Si desea cambiar el nombre del equipo después de unirse a un dominio, utilice el comando Cambiar nombre equipo PowerShell seguido por el nombre del equipo nuevo.
  
## <a name="see-also"></a>Vea también

#### 

[Requisitos de los sistemas de salas de Skype v2](requirements.md)
  
[Implementar sala de Skype v2 de sistemas](../../deploy/deploy-clients/room-systems-v2.md)
  
[Configurar una consola de sistemas de salas de Skype v2](../../deploy/deploy-clients/console.md)
  
[Administrar espacio de Skype v2 de sistemas](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

