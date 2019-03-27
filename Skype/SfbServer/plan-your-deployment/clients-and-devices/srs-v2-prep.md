---
title: Preparar el entorno
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
description: En este artículo se explica los preparativos de infraestructura para la implementación de sistemas de salón de Skype v2.
ms.openlocfilehash: 89c035816784bf160ad7f1ed821ed0effe916f31
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876075"
---
# <a name="prepare-your-environment"></a>Preparar el entorno

Esta sección contiene información general sobre los pasos necesarios para preparar su Skype para el entorno empresarial para que pueda usar todas las características de sistemas de salón de Skype v2.
  
1. Prepare una cuenta de dispositivo para cada consola v2 de sistemas de salón de Skype. Para obtener información detallada, vea [implementar sistemas de salón de Skype v2](../../deploy/deploy-clients/room-systems-v2.md) .
    
2. Asegúrese de que las conexiones de red y de Internet funcionen correctamente en el dispositivo que se va a utilizar.  
    
   - Debe ser capaz de recibir una dirección IP mediante DHCP (Nota: Skype salón sistemas v2 no se pueden configurar con una dirección IP estática en el primer inicio de unidad)
    
   - Debe tener estos puertos abiertos (además de abrir los puertos normales para los medios de Skype Empresarial):
    
   - HTTPS: 443
    
   - HTTP: 80
    
   - Si su red se ejecuta mediante un proxy, necesitará también la dirección del proxy o la información de script.
    
     > [!NOTE]
     > Sistemas de salón de Skype v2 no es compatible con entrada HDCP, que se ha observado para provocar problemas con HDMI ingesta funcionalidad (vídeo, audio). Tenga cuidado para asegurarse de que los conmutadores conectados a sistemas de salón de Skype v2 tienen opciones HDCP desactivadas. 
  
3. Para poder mejorar su experiencia, Microsoft recopila información. Para recopilar información, necesitamos que estos sitios figuren en la lista de permitidos:
    
   - Extremo de cliente de telemetría:https://vortex.data.microsoft.com/
    
   - Extremo de la configuración de telemetría:https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>Crear y probar una cuenta de dispositivo

Una *cuenta de dispositivo* es una cuenta que utiliza el cliente de v2 de sistemas de salón de Skype para tener acceso a las características de Exchange, al igual que el calendario y para habilitar Skype para la empresa. Para obtener información detallada, vea [implementar sistemas de salón de Skype v2](../../deploy/deploy-clients/room-systems-v2.md) .
  
### <a name="check-network-availability"></a>Comprobar la disponibilidad de red

Para que funcione correctamente, el dispositivo de v2 de sistemas de Skype sala debe tener acceso a una red por cable que cumple estos requisitos:
  
- Tener acceso a su instancia de Active Directory o Azure Active Directory (Azure AD), así como a sus servidores de Microsoft Exchange y Skype Empresarial.
    
- Tener acceso a un servidor que pueda proporcionar una dirección IP mediante DHCP. Sistemas de salón de Skype v2 no se puede configurar con una dirección IP estática.
    
- Tener acceso a los puertos HTTP 80 y 443.
    
- Puertos TCP y UDP configurados como se describe en [requisitos de protocolo y puerto para los servidores](../network-requirements/ports-and-protocols.md) para locales Skype para implementaciones empresariales o [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) para Skype para implementaciones en línea de negocio.
    
> [!IMPORTANT]
> Asegúrese de usar una conexión de red cableada de 1 Gbps para garantizar que dispondrá de la banda ancha necesaria.  
  
### <a name="certificates"></a>Certificados

Su dispositivo v2 de Skype salón sistemas utiliza certificados para los servicios Web Exchange, Skype para profesionales, el uso de la red y la autenticación. En el caso de que los servidores relacionados utilicen certificados públicos, como ocurre con las implementaciones en línea y algunas locales, no será necesario que el administrador realice ninguna otra acción en relación a la instalación de certificados. Si, por el contrario, la entidad de certificación es una CA privada (habitual en las instalaciones locales), el dispositivo necesita poder confiar en esa CA, lo que implica tener los certificados de la cadena CA + CA instalados en el dispositivo. Al añadir el dispositivo al dominio, esta tarea se realiza de forma automática.
  
Los certificados se instalarán del mismo modo en que se instalarían para cualquier otro cliente de Windows.  
  
> [!NOTE]
> Es posible que se requieren certificados con el fin de que tengan sistemas de salón de Skype v2 Skype para Business Server. 
  
### <a name="proxy"></a>Proxy

Sistemas de salón de Skype v2 está diseñado para heredar la configuración de Proxy del sistema operativo Windows. Acceda al SO Windows de la siguiente manera:
  
1. En la interfaz de usuario de sistemas de salón de Skype v2, haga clic en el icono de engranaje de configuración donde se le pedirá la contraseña de administrador local en el dispositivo (la contraseña predeterminada es **sfb**).
    
2. Puntee en **configuración** seguido de puntear en el botón **Ir a Windows** y, a continuación, puntee en el botón **Ir a inicio de sesión en el administrador** y, a continuación, haciendo clic en el botón de **Administrador** (si el equipo está unido al dominio elija **Otro usuario,** a continuación, usar . \admin como el nombre de usuario).
    
3. En las **Ventanas de búsqueda** del cuadro Tipo izquierdo inferior en regedit (ya sea durante cuánto tiempo presione la pantalla o botón secundario haga clic en y elija **Ejecutar como administrador**).
    
4. Haga clic en la carpeta HKEY_USERS (podrá ver una lista de identificadores de seguridad de los usuarios de la máquina), asegúrese de que la carpeta raíz HKEY_USERS esté seleccionada.
       
5. Haga clic en archivo y, a continuación, elija **Cargar subárbol.**
    
6. Examinar el a la **C:\Users\Skype** cuadro NTUSER.dat y presione el botón Abrir carpeta y escriba el nombre de archivo

7. Se le pedirá un nombre de clave para su subárbol recién cargada; Escriba en Skype (ahora debería ver la configuración del registro para el usuario de Skype).
 
8. Abra la clave de Skype y vaya a configuración de HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet, a continuación, asegúrese de que se escriben estas opciones de configuración: 
    
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    
    "MigrateProxy"=dword:00000001
    
    "ProxyEnable"=dword:00000001
    
    "ProxyServer"="xx.xx.xx.xx:8080"
    
    Si ProxyServer no existe, es posible que deba agregar esta clave como una cadena, cambie xx.xx.xx.xx:8080 a la dirección IP/host y al puerto de su servidor Proxy.
    
9. Una vez que haya terminado de realizar los cambios que resalte el usuario Skype clave (carpeta raíz de Skype) y elija Descargar sección en el menú archivo de registro (se le pedirá confirmación - seleccionar **Sí** ).
    
10. Ahora puede cerrar el editor del registro y escribir cerrar la sesión en el cuadro de búsqueda de Windows.
    
11. Nuevamente en la pantalla de inicio de sesión, elija el usuario de **Skype**. Si todos los pasos anteriores se realizaron correctamente, el dispositivo v2 de sistemas de salón de Skype se inicio de sesión correctamente.
    
Para usar esta aplicación, debe poder conectarse a los puntos de conexión que se describen a continuación. Para ver las direcciones IP, amplíe la sección de direcciones IP que se encuentra debajo de la tabla que describe el flujo de tráfico.
  
**Ejemplos de nombre de host del proxy del firewall/puerto**

|**Finalidad**|**Origen o credenciales**|**Puerto de origen**|**Destino**|**CDN**|**ExpressRoute para Office 365**|**IP de destino**|**Puerto de destino**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Autenticación e identidad  <br/> |Vea la [identidad y la autenticación de Office 365](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Identity) <br/> |||
|Portal e infraestructura compartida  <br/> |Vea [Office 365 del portal y compartida](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Portal-identity) <br/> |||
|Señalización de SIP  <br/> |Equipo cliente o usuario conectado  <br/> |Puertos efímeros  <br/> |\*. contoso.com  <br/> |No  <br/> |Sí  <br/> |[Skype para rangos IP empresarial](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Conferencia web de conexiones PSOM (modelo de objetos compartidos persistentes)  <br/> |Equipo cliente o usuario conectado  <br/> |Puertos efímeros  <br/> |\*. contoso.com  <br/> |No  <br/> |Sí  <br/> |[Skype para rangos IP empresarial](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Descargas HTTPS  <br/> |Equipo cliente o usuario conectado  <br/> |Puertos efímeros  <br/> |\*. contoso.com  <br/> |No  <br/> |Sí  <br/> |[Skype para rangos IP empresarial](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Audio  <br/> |Equipo cliente o usuario conectado  <br/> |TCP/UDP 50.000-50.019  <br/> |\*. contoso.com  <br/> |No  <br/> |Sí  <br/> |[Skype para rangos IP empresarial](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, UDP 3478, TCP/UDP 50.000-59.999  <br/> |
|Vídeo  <br/> |Equipo cliente o usuario conectado  <br/> |TCP/UDP 50.020-50.039  <br/> |\*. contoso.com  <br/> |No  <br/> |Sí  <br/> |[Skype para rangos IP empresarial](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, UDP 3478, TCP/UDP 50.000-59.999  <br/> |
|Compartir escritorio  <br/> |Equipo cliente o usuario conectado  <br/> |TCP/UDP 50.040-50.059  <br/> |\*. contoso.com  <br/> |No  <br/> |Sí  <br/> |[Skype para rangos IP empresarial](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, 50.000-59.999  <br/> |
|Notificaciones de inserción de Lync Mobile para Lync Mobile 2010 en dispositivos iOS. No es necesario para dispositivos móviles Android, Nokia Symbian o Windows Phone.  <br/> |Equipo cliente o usuario conectado  <br/> |Puertos efímeros  <br/> |\*. contoso.com  <br/> |No  <br/> |Sí  <br/> |[Skype para rangos IP empresarial](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 5223  <br/> |
|Telemetría de Skype  <br/> |Equipo cliente o usuario conectado  <br/> |Puertos efímeros  <br/> |skypemaprdsitus.trafficmanager.net  <br/> pipe.skype.com  <br/> |No  <br/> |No  <br/> |N/D  <br/> |TCP 443  <br/> |
|Sugerencias rápidas del cliente de Skype  <br/> |Equipo cliente o usuario conectado  <br/> |Puertos efímeros  <br/> |quicktips.skypeforbusiness.com  <br/> |No  <br/> |No  <br/> |N/D  <br/> |TCP 443  <br/> |
   
> [!NOTE]
> El carácter comodín de contoso.com y broadcast.skype.com representa una larga lista de nodos que se utilizan en exclusividad para Office 365. 
  
### <a name="create-provisioning-packages"></a>Crear paquetes de aprovisionamiento

Paquetes de aprovisionamiento va a usar para autenticar al servidor de Exchange o Skype para Business Server.
  
### <a name="admin-group-management"></a>Administración del grupo de administradores

Después de la unión a un dominio, puede usar la Directiva de grupo o la Administración del equipo local para configurar un Grupo de seguridad como administrador local, tal como lo haría para un PC con Windows en su dominio. Las personas que formen parte de ese grupo de seguridad podrán introducir sus credenciales y desbloquear Configuración.
  
> [!NOTE]
> Si su dispositivo v2 de sistemas de salón de Skype pierde la relación de confianza con el dominio (por ejemplo, si quita el v2 de sistemas de salón de Skype desde el dominio después de está unido al dominio), no podrá autenticar en el dispositivo y abrir seguridad de la configuración. La solución alternativa es iniciar sesión con la cuenta de administrador local. 
  
## <a name="local-accounts"></a>Cuentas locales

### <a name="skype-room-systems-local-user-account"></a>Cuenta de usuario local de Sistemas de salas de Skype

Normalmente, la cuenta de dispositivo no requiere una contraseña. Es posible asignarle una, pero acarrea consecuencias, como que los usuarios se puedan quedar bloqueados fuera de la aplicación de consola cuando expire la contraseña. Por lo tanto, el administrador debe garantizar que la contraseña no esté configurada para que expire.
  
### <a name="admin---local-administrator-account"></a>"Administrador": cuenta de administrador local

Contraseña de Skype salón sistemas v2 de forma predeterminada se establece en "sfb". Puede cambiar la contraseña localmente, vaya a configuración de Windows \> vaya a Windows o en el archivo AutoUnattend.xml (use el Administrador de la imagen de sistema de Windows desde ADK para realizar el cambio en el archivo xml).
  
> [!CAUTION]
> Asegúrese de cambiar la contraseña de v2 de Skype salón sistemas tan pronto como sea posible. 
  
Otra manera de administrar la contraseña de administrador local es configurar una directiva de grupo en la que los administradores de dominio se conviertan en administradores locales.
  
La contraseña del administrador local no se incluye como opción durante la configuración.
  
### <a name="machine-account"></a>Cuenta de equipo

Mucho al igual que cualquier dispositivo de Windows, el nombre del equipo puede cambiarse haciendo clic en configuración de \> sobre \> cambiar el nombre de PC.
  
 Si desea cambiar el nombre del equipo después de unirse a un dominio, use el comando de PowerShell de cambio de nombre de equipo seguido por el nombre del equipo nuevo.
  
## <a name="see-also"></a>Consulte también

[Planeación de la sala de Skype v2 de sistemas](skype-room-systems-v2-0.md)

[Requisitos de Sistemas de salas de Skype v2](requirements.md)
  
[Implementar Sistemas de salas de Skype v2](../../deploy/deploy-clients/room-systems-v2.md)
  
[Configurar una consola de Sistemas de salas de Skype v2](../../deploy/deploy-clients/console.md)
  
[Administrar Sistemas de salas de Skype v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)
