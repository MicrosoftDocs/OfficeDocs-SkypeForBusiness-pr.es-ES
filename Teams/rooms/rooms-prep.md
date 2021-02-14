---
title: Preparar el entorno
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo preparar su infraestructura para implementar Salas de Microsoft Teams para que pueda aprovechar todas las características.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d0c5d5a1b0333a30b7730d6c8b91d06e67e291b4
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662435"
---
# <a name="prepare-your-environment"></a>Preparar el entorno

Esta sección contiene información general de los pasos necesarios para preparar el entorno de modo que pueda usar todas las características de Salas de Microsoft Teams.
  
1. Prepare una cuenta de dispositivo para cada consola de Salas de Microsoft Teams. Consulte [Implementar salas de Microsoft Teams](rooms-deploy.md) para obtener más información.
    
2. Asegúrese de que las conexiones de red y de Internet funcionen correctamente en el dispositivo que se va a utilizar.  
    
   - Debe poder recibir una dirección IP mediante LAN. (No se pueden configurar salas de Microsoft Teams con una dirección IP estática en el primer inicio de la unidad, pero posteriormente se podría configurar la IP estática del dispositivo en el dispositivo o en el conmutador de subida o enrutador).
   - Debe tener estos puertos abiertos (además de abrir los puertos normales para los medios):
   - HTTPS: 443
   - HTTP: 80
   - Si su red se ejecuta mediante un proxy, necesitará también la dirección del proxy o la información de script.
    
     > [!IMPORTANT]
     > Los salas de Microsoft Teams no admiten la autenticación de proxy, ya que puede interferir con operaciones regulares de la sala. Asegúrese de que los salas de Microsoft Teams están exentos de la autenticación de proxy antes de entrar en producción.
  
3. Para poder mejorar su experiencia, Microsoft recopila información. Para permitir que Microsoft recopile datos, permita estos sitios:

   - Extremo del cliente de telemetría: https://vortex.data.microsoft.com/
   - Extremo de configuración de telemetría: https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>Crear y probar una cuenta de dispositivo

Una  *cuenta de dispositivo*  es una cuenta que el cliente de salas de Microsoft Teams usa para acceder a características de Exchange, como el calendario, y para habilitar Skype Empresarial. Consulte [Implementar salas de Microsoft Teams](rooms-deploy.md) para obtener más información.
  
### <a name="check-network-availability"></a>Comprobar la disponibilidad de red

Para funcionar correctamente, el dispositivo de Salas de Microsoft Teams debe tener acceso a una red cableada que cumpla estos requisitos:
  
- Tener acceso a su instancia de Active Directory o Azure Active Directory (Azure AD), así como a sus servidores de Microsoft Exchange y Skype Empresarial.
- Tener acceso a un servidor que pueda proporcionar una dirección IP mediante DHCP. No se pueden configurar salas de Microsoft Teams con una dirección IP estática en el primer inicio de la unidad.
- Tener acceso a los puertos HTTP 80 y 443.
- Puertos TCP y UDP [](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) configurados como se describe en los requisitos de puerto y protocolo para los servidores para implementaciones locales de Skype Empresarial Server, o direcciones URL e intervalos de direcciones IP de [Microsoft 365 y Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) para implementaciones en línea de Microsoft Teams o Skype Empresarial.

> [!IMPORTANT]
> Asegúrese de usar una conexión de red cableada de 1 Gbps para garantizar que dispondrá de la banda ancha necesaria. 

> [!NOTE]
> Las actualizaciones de software para salas de Microsoft Teams se descargan automáticamente desde Microsoft Store para Empresas. Consulte [los requisitos previos](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) de Microsoft Store para Empresas y Educación para comprobar que la consola de la sala pueda tener acceso a la tienda y actualizarse automáticamente.
  
### <a name="certificates"></a>Certificados

Su dispositivo de salas de Microsoft Teams usa certificados para servicios web de Exchange, Microsoft Teams o Skype Empresarial, uso de red y autenticación. En el caso de que los servidores relacionados utilicen certificados públicos, como ocurre con las implementaciones en línea y algunas locales, no será necesario que el administrador realice ninguna otra acción en relación a la instalación de certificados. Si, por el contrario, la entidad de certificación es una CA privada (habitual en las instalaciones locales), el dispositivo necesita poder confiar en esa CA, lo que implica tener los certificados de la cadena CA + CA instalados en el dispositivo. Al añadir el dispositivo al dominio, esta tarea se realiza de forma automática.
  
Los certificados se instalarán del mismo modo en que se instalarían para cualquier otro cliente de Windows.  
  
> [!NOTE]
> Es posible que se requieran certificados para que las salas de Microsoft Teams usen Skype Empresarial Server.
  
### <a name="proxy"></a>Proxy

Microsoft Teams Rooms está diseñado para heredar la configuración de proxy del sistema operativo Windows. Acceda al SO Windows de la siguiente manera:
  
1. En la interfaz de usuario de salas de Microsoft Teams, haga clic en el icono de engranaje de Configuración, donde se le pedirá la contraseña del administrador local en el dispositivo (la contraseña predeterminada es **sfb).**
2. Pulse  Configuración seguido del botón Ir a **Windows** y, a continuación, pulse  en el botón Ir a Inicio de sesión de administrador y, a continuación, haga clic en el botón Administrador (si el equipo está unido a un dominio, elija Otro usuario y, a  **continuación,** use .\admin como nombre de usuario).
3. En el **cuadro buscar en Windows,** escriba en regedit (pulse la pantalla varios veces o haga clic con el botón derecho y elija **Ejecutar como administrador).**
4. Haga clic en la carpeta HKEY_USERS (podrá ver una lista de identificadores de seguridad de los usuarios de la máquina), asegúrese de que la carpeta raíz HKEY_USERS esté seleccionada.
       
5. Haga clic en Archivo y elija **Cargar subárbol.**
6. Vaya a la carpeta **C:\Users\Skype** y escriba en el cuadro Nombre de archivo NTUSER.dat y presione el botón Abrir.

7. Se le pedirá un nombre de clave para el subárbol cargado recientemente; escribe en Skype (ahora deberías ver la configuración del Registro del Usuario de Skype).
 
8. Abre la tecla Skype y busca HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings que se introduce esta configuración: 
    
    `[HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]`
    
    `"MigrateProxy"=dword:00000001`
    
    `"ProxyEnable"=dword:00000001`
    
    `"ProxyServer"="xx.xx.xx.xx:8080"`
    
    Si ProxyServer no existe, es posible que deba agregar esta clave como una cadena, cambie xx.xx.xx.xx:8080 a la dirección IP/host y al puerto de su servidor Proxy.
    
9. Cuando haya terminado de realizar los cambios, resalte la clave de usuario de Skype (carpeta raíz de Skype) y elija descargar subárbol desde el menú Archivo del Registro (se le pedirá confirmación, seleccione **Sí).**
    
10. Ahora puede cerrar el editor del registro y escribir cerrar la sesión en el cuadro de búsqueda de Windows.
    
11. Nuevamente en la pantalla de inicio de sesión, elija el usuario de **Skype**. Si todos los pasos anteriores se completaron correctamente, el dispositivo salas de Microsoft Teams iniciará sesión correctamente.
    
Para usar esta aplicación, debe poder conectarse a los puntos de conexión que se describen a continuación. Para ver las direcciones IP, amplíe la sección de direcciones IP que se encuentra debajo de la tabla que describe el flujo de tráfico.
  
**Ejemplos de nombre de host del proxy del firewall/puerto**

|Finalidad|Origen o credenciales|Puerto de origen|Destino|CDN|ExpressRoute para Office 365|IP de destino|Puerto de destino|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Autenticación e identidad  <br/> |Ver [autenticación e identidad de Microsoft 365 y Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Identity) <br/> |||
|Portal e infraestructura compartida  <br/> |Ver [el Centro de administración de Microsoft 365 y compartir](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Portal-identity) <br/> |||
|Señalización de SIP  <br/> |Equipo cliente o usuario conectado  <br/> |Puertos efímeros  <br/> |\*.contoso.com  <br/> |No  <br/> |Sí  <br/> |[Intervalos IP de Skype Empresarial](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Conferencia web de conexiones PSOM (modelo de objetos compartidos persistentes)  <br/> |Equipo cliente o usuario conectado  <br/> |Puertos efímeros  <br/> |\*.contoso.com  <br/> |No  <br/> |Sí  <br/> |[Intervalos IP de Skype Empresarial](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Descargas HTTPS  <br/> |Equipo cliente o usuario conectado  <br/> |Puertos efímeros  <br/> |\*.contoso.com  <br/> |No  <br/> |Sí  <br/> |[Intervalos IP de Skype Empresarial](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Audio  <br/> |Equipo cliente o usuario conectado  <br/> |TCP/UDP 50.000-50.019  <br/> |\*.contoso.com  <br/> |No  <br/> |Sí  <br/> |[Intervalos IP de Skype Empresarial](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, UDP 3478, TCP/UDP 50.000-59.999  <br/> |
|Vídeo  <br/> |Equipo cliente o usuario conectado  <br/> |TCP/UDP 50.020-50.039  <br/> |\*.contoso.com  <br/> |No  <br/> |Sí  <br/> |[Intervalos IP de Skype Empresarial](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, UDP 3478, TCP/UDP 50.000-59.999  <br/> |
|Compartir escritorio  <br/> |Equipo cliente o usuario conectado  <br/> |TCP/UDP 50.040-50.059  <br/> |\*.contoso.com  <br/> |No  <br/> |Sí  <br/> |[Intervalos IP de Skype Empresarial](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, 50.000-59.999  <br/> |
|Notificaciones de inserción de Lync Mobile para Lync Mobile 2010 en dispositivos iOS. No es necesario para dispositivos móviles Android, Nokia Symbian o Windows Phone.  <br/> |Equipo cliente o usuario conectado  <br/> |Puertos efímeros  <br/> |\*.contoso.com  <br/> |No  <br/> |Sí  <br/> |[Intervalos IP de Skype Empresarial](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 5223  <br/> |
|Telemetría de Skype  <br/> |Equipo cliente o usuario conectado  <br/> |Puertos efímeros  <br/> |skypemaprdsitus.trafficmanager.net  <br/> pipe.skype.com  <br/> |No  <br/> |No  <br/> |N/D  <br/> |TCP 443  <br/> |
|Sugerencias rápidas del cliente de Skype  <br/> |Equipo cliente o usuario conectado  <br/> |Puertos efímeros  <br/> |quicktips.skypeforbusiness.com  <br/> |No  <br/> |No  <br/> |N/D  <br/> |TCP 443  <br/> |

> [!NOTE]
> El carácter comodín contoso.com y broadcast.skype.com representa una lista larga de nodos que se usan exclusivamente para Microsoft 365 u Office 365. 
  
### <a name="create-provisioning-packages"></a>Crear paquetes de aprovisionamiento

Usará el aprovisionamiento de paquetes para autenticar Exchange Server, Microsoft 365 u Office 365.
  
### <a name="admin-group-management"></a>Administración del grupo de administradores

Después de la unión a un dominio, puede usar la Directiva de grupo o la Administración del equipo local para configurar un Grupo de seguridad como administrador local, tal como lo haría para un PC con Windows en su dominio. Las personas que formen parte de ese grupo de seguridad podrán introducir sus credenciales y desbloquear Configuración.
  
> [!NOTE]
> Si su dispositivo de Sala de Microsoft Teams pierde la confianza en el dominio (por ejemplo, si elimina Sala de Microsoft Teams del dominio tras haberse unido a él), no podrá autenticarse en el dispositivo ni abrir Configuración. La solución alternativa es iniciar sesión con la cuenta de administrador local. 
  
## <a name="local-accounts"></a>Cuentas locales

### <a name="microsoft-teams-rooms-local-user-account"></a>Cuenta de usuario local de Microsoft Teams Rooms

Normalmente, la cuenta de dispositivo no requiere una contraseña. Es posible asignarle una, pero acarrea consecuencias, como que los usuarios se puedan quedar bloqueados fuera de la aplicación de consola cuando expire la contraseña. Por lo tanto, el administrador debe garantizar que la contraseña no esté configurada para que expire.
  
### <a name="admin---local-administrator-account"></a>"Administrador": cuenta de administrador local

La contraseña predeterminada de los salas de Microsoft Teams se establece en "sfb". La contraseña se puede cambiar localmente yendo a la configuración de Windows, ve a Windows o en el archivo AutoUnattend.xml (usa el Administrador de imágenes del sistema de Windows de ADK para realizar el cambio al \> archivo xml).
  
> [!CAUTION]
> Asegúrese de cambiar la contraseña de los salas de Microsoft Teams lo antes posible. 
  
Otra manera de administrar la contraseña de administrador local es configurar una directiva de grupo en la que los administradores de dominio se conviertan en administradores locales.
  
La contraseña del administrador local no se incluye como opción durante la configuración.
  
### <a name="machine-account"></a>Cuenta de equipo

Como en cualquier dispositivo Windows, se puede cambiar el nombre del equipo haciendo clic con el botón derecho en Configuración acerca de cambiar el nombre \> \> del equipo.
  
 Si desea cambiar el nombre del equipo después de unirse a un dominio, use el comando Rename-Computer PowerShell seguido del nombre nuevo del equipo.
  
## <a name="related-topics"></a>Temas relacionados

[Planear salas de Microsoft Teams](rooms-plan.md)

[Requisitos de la sala de Microsoft Teams](requirements.md)
  
[Implementar Salas de Microsoft Teams](rooms-deploy.md)
  
[Configurar una consola de sala de Microsoft Teams](console.md)
  
[Administrar Salas de Microsoft Teams](rooms-manage.md)

[Requisitos previos para Microsoft Store para Empresas y Educación](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) 
