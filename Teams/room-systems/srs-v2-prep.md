---
title: Preparar el entorno
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
description: En este artículo se explican los preparativos de infraestructura para implementar salas de Microsoft Teams.
ms.openlocfilehash: b7bc3b7791edf88fd6882b67cdaa7d9b65e87741
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2019
ms.locfileid: "38675808"
---
# <a name="prepare-your-environment"></a>Preparar el entorno

Esta sección contiene una descripción general de los pasos necesarios para preparar el entorno para poder usar todas las características de las salas de Microsoft Teams.
  
1. Prepare una cuenta de dispositivo para cada consola de salas de Microsoft Teams. Consulte [implementar salas de Microsoft Teams](room-systems-v2.md) para obtener más información.
    
2. Asegúrese de que las conexiones de red y de Internet funcionen correctamente en el dispositivo que se va a utilizar.  
    
   - Debe poder recibir una dirección IP usando DHCP. (Las salas de Microsoft Teams no se pueden configurar con una dirección IP estática en el primer inicio de la unidad, pero después se puede configurar la IP estática en el dispositivo o en el conmutador o enrutador de nivel superior).
   - Debe tener estos puertos abiertos (además de abrir los puertos normales de medios):
   - HTTPS: 443
   - HTTP: 80
   - Si su red se ejecuta mediante un proxy, necesitará también la dirección del proxy o la información de script.
    
     > [!NOTE]
     > Sala de Microsoft Teams no admite la incorporación de HDCP, ya que se ha visto que provoca problemas con la funcionalidad de transmisión por HDMI (vídeo, audio). Asegúrese de que los conmutadores conectados a Sala de Microsoft Teams tienen desactivadas las opciones de HDCP.
  
3. Para poder mejorar su experiencia, Microsoft recopila información. Para permitir que Microsoft recopile datos, lista blanca estos sitios:

   - Extremo del cliente de telemetría:https://vortex.data.microsoft.com/
   - Punto de conexión de configuración de telemetría:https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>Crear y probar una cuenta de dispositivo

Una *cuenta de dispositivo* es una cuenta que usa el cliente de Microsoft Teams Rooms para acceder a características de Exchange, como el calendario, y para habilitar Skype empresarial. Consulte [implementar salas de Microsoft Teams](room-systems-v2.md) para obtener más información.
  
### <a name="check-network-availability"></a>Comprobar la disponibilidad de red

Para que funcione correctamente, el dispositivo de las salas de Microsoft Teams debe tener acceso a una red cableada que cumpla con estos requisitos:
  
- Tener acceso a su instancia de Active Directory o Azure Active Directory (Azure AD), así como a sus servidores de Microsoft Exchange y Skype Empresarial.
- Tener acceso a un servidor que pueda proporcionar una dirección IP mediante DHCP. Las salas de Microsoft Teams no se pueden configurar con una dirección IP estática.
- Tener acceso a los puertos HTTP 80 y 443.
- Puertos TCP y UDP configurados según se describe en [requisitos de puertos y protocolos para servidores](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) de implementaciones locales de Skype empresarial Server u [Office 365 URL e intervalos de direcciones IP](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) para Microsoft Teams o implementaciones de Skype empresarial online.

> [!IMPORTANT]
> Asegúrese de usar una conexión de red cableada de 1 Gbps para garantizar que dispondrá de la banda ancha necesaria. 

> [!NOTE]
> Las actualizaciones de software para Microsoft Team Rooms se descargan automáticamente de Microsoft Store para empresas. Consulte los [requisitos previos de Microsoft Store para empresas y educación](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) para comprobar que la consola de la sala podrá acceder a la tienda y a la actualización automática.
  
### <a name="certificates"></a>Certificados

Su dispositivo de salas de Microsoft Teams usa certificados para servicios web Exchange, Microsoft Teams o Skype empresarial, uso de red y autenticación. En el caso de que los servidores relacionados utilicen certificados públicos, como ocurre con las implementaciones en línea y algunas locales, no será necesario que el administrador realice ninguna otra acción en relación a la instalación de certificados. Si, por el contrario, la entidad de certificación es una CA privada (habitual en las instalaciones locales), el dispositivo necesita poder confiar en esa CA, lo que implica tener los certificados de la cadena CA + CA instalados en el dispositivo. Al añadir el dispositivo al dominio, esta tarea se realiza de forma automática.
  
Los certificados se instalarán del mismo modo en que se instalarían para cualquier otro cliente de Windows.  
  
> [!NOTE]
> Es posible que se necesiten certificados para que las salas de Microsoft Teams usen Skype empresarial Server.
  
### <a name="proxy"></a>Proxy

Salas de Microsoft Teams se ha diseñado para heredar la configuración de proxy del sistema operativo Windows. Acceda al SO Windows de la siguiente manera:
  
1. En la interfaz de usuario de salas de Microsoft Teams, haga clic en el icono de engranaje de configuración donde se le solicitará la contraseña del administrador local en el dispositivo (la contraseña predeterminada es **SFB**).
2. Puntee en **configuración** seguido de puntear en el botón **ir a Windows** y, después, en el botón **ir a Inicio de sesión de administrador** y, a continuación, haga clic en el botón **Administrador** (si el equipo está unido a un **usuario,** use .\ADMIN como nombre de usuario).
3. En el cuadro **Buscar ventanas** de la parte inferior izquierda, en regedit (Presione la pantalla o haga clic con el botón derecho y elija **Ejecutar como administrador**).
4. Haga clic en la carpeta HKEY_USERS (podrá ver una lista de identificadores de seguridad de los usuarios de la máquina), asegúrese de que la carpeta raíz HKEY_USERS esté seleccionada.
       
5. Haga clic en archivo y, a continuación, elija **Cargar subárbol.**
6. Vaya a la carpeta **C:\Users\Skype** y escriba el nombre de archivo Ntuser. dat y haga clic en el botón abrir.

7. Se le pedirá un nombre de clave para el nuevo subárbol cargado. escribe Skype (ahora deberías ver la configuración del registro para el usuario de Skype).
 
8. Abra la clave de Skype y vaya a HKEY_USERS configuración de \Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Asegúrese de que se ha introducido esta configuración: 
    
    `[HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]`
    
    `"MigrateProxy"=dword:00000001`
    
    `"ProxyEnable"=dword:00000001`
    
    `"ProxyServer"="xx.xx.xx.xx:8080"`
    
    Si ProxyServer no existe, es posible que deba agregar esta clave como una cadena, cambie xx.xx.xx.xx:8080 a la dirección IP/host y al puerto de su servidor Proxy.
    
9. Una vez que haya terminado de realizar los cambios, resalte la clave de usuario de Skype (carpeta raíz de Skype) y elija descargar sección en el menú Archivo del registro (se le solicitará **confirmación).**
    
10. Ahora puede cerrar el editor del registro y escribir cerrar la sesión en el cuadro de búsqueda de Windows.
    
11. Nuevamente en la pantalla de inicio de sesión, elija el usuario de **Skype**. Si todos los pasos anteriores se realizaron correctamente, el dispositivo salas de Microsoft Teams se iniciará correctamente.
    
Para usar esta aplicación, debe poder conectarse a los puntos de conexión que se describen a continuación. Para ver las direcciones IP, amplíe la sección de direcciones IP que se encuentra debajo de la tabla que describe el flujo de tráfico.
  
**Ejemplos de nombre de host del proxy del firewall/puerto**

|Finalidad|Origen o credenciales|Puerto de origen|Destino|CDN|ExpressRoute para Office 365|IP de destino|Puerto de destino|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Autenticación e identidad  <br/> |Consulte [autenticación e identidad de Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Identity) <br/> |||
|Portal e infraestructura compartida  <br/> |Consulte [portal de Office 365 y uso compartido](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Portal-identity) <br/> |||
|Señalización de SIP  <br/> |Equipo cliente o usuario conectado  <br/> |Puertos efímeros  <br/> |\*. contoso.com  <br/> |No  <br/> |Sí  <br/> |[Intervalos IP de Skype empresarial](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Conferencia web de conexiones PSOM (modelo de objetos compartidos persistentes)  <br/> |Equipo cliente o usuario conectado  <br/> |Puertos efímeros  <br/> |\*. contoso.com  <br/> |No  <br/> |Sí  <br/> |[Intervalos IP de Skype empresarial](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Descargas HTTPS  <br/> |Equipo cliente o usuario conectado  <br/> |Puertos efímeros  <br/> |\*. contoso.com  <br/> |No  <br/> |Sí  <br/> |[Intervalos IP de Skype empresarial](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Audio  <br/> |Equipo cliente o usuario conectado  <br/> |TCP/UDP 50.000-50.019  <br/> |\*. contoso.com  <br/> |No  <br/> |Sí  <br/> |[Intervalos IP de Skype empresarial](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, UDP 3478, TCP/UDP 50.000-59.999  <br/> |
|Vídeo  <br/> |Equipo cliente o usuario conectado  <br/> |TCP/UDP 50.020-50.039  <br/> |\*. contoso.com  <br/> |No  <br/> |Sí  <br/> |[Intervalos IP de Skype empresarial](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, UDP 3478, TCP/UDP 50.000-59.999  <br/> |
|Compartir escritorio  <br/> |Equipo cliente o usuario conectado  <br/> |TCP/UDP 50.040-50.059  <br/> |\*. contoso.com  <br/> |No  <br/> |Sí  <br/> |[Intervalos IP de Skype empresarial](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, 50.000-59.999  <br/> |
|Notificaciones de inserción de Lync Mobile para Lync Mobile 2010 en dispositivos iOS. No es necesario para dispositivos móviles Android, Nokia Symbian o Windows Phone.  <br/> |Equipo cliente o usuario conectado  <br/> |Puertos efímeros  <br/> |\*. contoso.com  <br/> |No  <br/> |Sí  <br/> |[Intervalos IP de Skype empresarial](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 5223  <br/> |
|Telemetría de Skype  <br/> |Equipo cliente o usuario conectado  <br/> |Puertos efímeros  <br/> |skypemaprdsitus.trafficmanager.net  <br/> pipe.skype.com  <br/> |No  <br/> |No  <br/> |N/D  <br/> |TCP 443  <br/> |
|Sugerencias rápidas del cliente de Skype  <br/> |Equipo cliente o usuario conectado  <br/> |Puertos efímeros  <br/> |quicktips.skypeforbusiness.com  <br/> |No  <br/> |No  <br/> |N/D  <br/> |TCP 443  <br/> |

> [!NOTE]
> El carácter comodín de contoso.com y broadcast.skype.com representa una larga lista de nodos que se utilizan en exclusividad para Office 365. 
  
### <a name="create-provisioning-packages"></a>Crear paquetes de aprovisionamiento

Usará paquetes de aprovisionamiento para autenticar a Exchange Server u Office 365.
  
### <a name="admin-group-management"></a>Administración del grupo de administradores

Después de la unión a un dominio, puede usar la Directiva de grupo o la Administración del equipo local para configurar un Grupo de seguridad como administrador local, tal como lo haría para un PC con Windows en su dominio. Las personas que formen parte de ese grupo de seguridad podrán introducir sus credenciales y desbloquear Configuración.
  
> [!NOTE]
> Si su dispositivo de Sala de Microsoft Teams pierde la confianza en el dominio (por ejemplo, si elimina Sala de Microsoft Teams del dominio tras haberse unido a él), no podrá autenticarse en el dispositivo ni abrir Configuración. La solución alternativa es iniciar sesión con la cuenta de administrador local. 
  
## <a name="local-accounts"></a>Cuentas locales

### <a name="microsoft-teams-rooms-local-user-account"></a>Sala de usuarios locales de Microsoft Teams

Normalmente, la cuenta de dispositivo no requiere una contraseña. Es posible asignarle una, pero acarrea consecuencias, como que los usuarios se puedan quedar bloqueados fuera de la aplicación de consola cuando expire la contraseña. Por lo tanto, el administrador debe garantizar que la contraseña no esté configurada para que expire.
  
### <a name="admin---local-administrator-account"></a>"Administrador": cuenta de administrador local

Salas de Microsoft teams la contraseña predeterminada está establecida en "SFB". La contraseña se puede cambiar de forma local en configuración \> de Windows, ir a Windows o en el archivo AutoUnattend. XML (use el administrador de imágenes de sistema de Windows de ADK para realizar el cambio en el archivo XML).
  
> [!CAUTION]
> Asegúrese de cambiar la contraseña de Microsoft Teams Rooms lo antes posible. 
  
Otra manera de administrar la contraseña de administrador local es configurar una directiva de grupo en la que los administradores de dominio se conviertan en administradores locales.
  
La contraseña del administrador local no se incluye como opción durante la configuración.
  
### <a name="machine-account"></a>Cuenta de equipo

Al igual que en cualquier dispositivo de Windows, se puede cambiar el nombre del equipo haciendo \> clic \> con el botón derecho en configuración para cambiar el nombre del equipo.
  
 Si desea cambiar el nombre del equipo después de unirme a un dominio, use el comando Rename-Computer PowerShell seguido del nombre nuevo del equipo.
  
## <a name="see-also"></a>Vea también

[Planear salas de Microsoft Teams](skype-room-systems-v2-0.md)

[Requisitos de salas de Microsoft Teams](requirements.md)
  
[Implementar salas de Microsoft Teams](room-systems-v2.md)
  
[Configurar una consola de salas de Microsoft Teams](console.md)
  
[Administrar Salas de Microsoft Teams](skype-room-systems-v2.md)

[Requisitos previos de Microsoft Store para empresas y educación](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) 
