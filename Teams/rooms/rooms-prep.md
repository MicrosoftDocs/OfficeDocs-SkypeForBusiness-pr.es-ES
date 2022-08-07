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
ms.localizationpriority: medium
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: Obtenga información sobre cómo preparar la infraestructura para implementar Salas de Microsoft Teams de modo que pueda aprovechar todas las características.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3f0224ebf0c6c8e0f21fe669bb8a92ff345b928b
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268955"
---
# <a name="prepare-your-environment"></a>Preparar el entorno

Esta sección contiene una descripción general de los pasos necesarios para preparar el entorno para que pueda usar todas las características de Salas de Microsoft Teams.
  
1. Prepare una cuenta de recursos para cada Salas de Microsoft Teams consola. Consulte [Implementar Salas de Microsoft Teams](rooms-deploy.md) para obtener más información.
    
2. Asegúrese de que las conexiones de red y de Internet funcionen correctamente en el dispositivo que se va a utilizar. 
  
3. Para poder mejorar su experiencia, Microsoft recopila información. Para permitir que Microsoft recopile datos, permita estos sitios:

   - Extremo del cliente de telemetría: `https://vortex.data.microsoft.com/`
   - Extremo de configuración de telemetría:` https://settings.data.microsoft.com/`
    
### <a name="create-and-test-a-resource-account"></a>Crear y probar una cuenta de recursos

Una *cuenta de recursos* es una cuenta que el cliente de Salas de Microsoft Teams usa para acceder a características de Exchange, como el calendario, y para conectarse a Microsoft Teams. Consulte [Implementar Salas de Microsoft Teams](rooms-deploy.md) para obtener más información.
  
### <a name="check-network-availability"></a>Comprobar la disponibilidad de red

Para funcionar correctamente, Salas de Microsoft Teams deben tener acceso a una red cableada que cumpla estos requisitos:
  
- Acceso a su instancia de Active Directory o Azure Active Directory (Azure AD), así como a Microsoft Exchange y Microsoft Teams.

- Tener acceso a un servidor que pueda proporcionar una dirección IP mediante DHCP. Salas de Microsoft Teams no se puede configurar con una dirección IP estática en el inicio de la primera unidad.

- Tener acceso a los puertos HTTP 80 y 443.

- Puertos TCP y UDP configurados como se describe en [Requisitos de puertos y protocolos para servidores](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) para implementaciones de Skype Empresarial Server locales, o [Microsoft 365 y Office 365 DIRECCIONES URL e intervalos de direcciones IP](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) para Microsoft Teams.

Si su red se ejecuta mediante un proxy, necesitará también la dirección del proxy o la información de script.
    
> [!IMPORTANT]
> Salas de Microsoft Teams no admite la autenticación de proxy, ya que puede interferir con las operaciones normales de la sala. Asegúrese de que Salas de Microsoft Teams se hayan exento de la autenticación de proxy antes de entrar en producción.

> [!IMPORTANT]
> Asegúrese de usar una conexión de red cableada de 1 Gbps para garantizar que dispondrá de la banda ancha necesaria. 

> [!NOTE]
> Las actualizaciones de software para Salas de Microsoft Teams se descargan automáticamente desde el Microsoft Store para Empresas. Consulte [Requisitos previos para Microsoft Store para Empresas y Educación](/microsoft-store/prerequisites-microsoft-store-for-business) para comprobar que la consola de la sala podrá acceder a la tienda y la actualización automática.
  
### <a name="certificates"></a>Certificados

El dispositivo de Salas de Microsoft Teams usa certificados para los servicios web de Exchange, Microsoft Teams o Skype for Business, el uso de red y la autenticación. Si los servidores relacionados usan certificados públicos, que es el caso para implementaciones en línea y algunas implementaciones locales, no debe haber ninguna acción adicional necesaria por parte del administrador para instalar certificados. Si, por otro lado, la entidad emisora de certificados es una CA privada, el dispositivo debe confiar en esa CA. Esto significa tener los certificados de cadena ca + CA instalados en el dispositivo. Al añadir el dispositivo al dominio, esta tarea se realiza de forma automática.
  
Los certificados se instalarán del mismo modo en que se instalarían para cualquier otro cliente de Windows. 

> [!IMPORTANT]
> Si el servidor proxy utiliza certificados firmados internamente, debe instalar la cadena de certificados interna, incluida la CA raíz, en el dispositivo Salas de Microsoft Teams.
  
> [!NOTE]
> Los certificados pueden ser necesarios para que Salas de Microsoft Teams utilicen Skype Empresarial Server.
  
### <a name="proxy"></a>Proxy

Salas de Microsoft Teams está diseñado para heredar la configuración de Proxy del sistema operativo Windows. Acceda al SO Windows de la siguiente manera:
  
1. En la interfaz de usuario de Salas de Microsoft Teams, haz clic en el icono de engranaje Configuración, donde se te pedirá la contraseña de administrador local en el dispositivo (la contraseña predeterminada es **sfb**).
2. Pulsa en **Configuración**, después pulsa en el botón **Ir a Windows** y, a continuación, pulsa en el botón **Ir a Administración Iniciar sesión** y, a continuación, haz clic en el botón **Administrador** (si el equipo está unido a un dominio **, elige Otro usuario y,** a continuación, usa .\admin como nombre de usuario).
3. En el cuadro **Buscar en Windows** de la parte inferior izquierda, escriba regedit (mantenga presionada la pantalla o haga clic con el botón derecho y elija **Ejecutar como administrador**).
4. Haga clic en la carpeta HKEY_USERS (podrá ver una lista de identificadores de seguridad de los usuarios de la máquina), asegúrese de que la carpeta raíz HKEY_USERS esté seleccionada.
       
5. Haga clic en Archivo y, a continuación, elija **Cargar subárbol.**
6. Vaya a la carpeta **C:\Users\Skype** , escriba en el cuadro Nombre de archivo NTUSER.dat y presione el botón Abrir.

7. Se le pedirá un Nombre de Clave para su Subárbol recién cargado; en Skype (ahora debería ver la configuración del Registro del usuario de Skype).
 
8. Abre la tecla Skype, busca HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings, a continuación, asegúrate de que se especifique esta configuración: 
    
    ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "ProxyServer"="xx.xx.xx.xx:8080"
    ```
    
    Si ProxyServer no existe, es posible que deba agregar esta clave como una cadena, cambie xx.xx.xx.xx:8080 a la dirección IP/host y al puerto de su servidor Proxy.
 
    Si el cliente usa un archivo PAC, la configuración sería similar a la del ejemplo siguiente:

     ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "AutoConfigURL"=http://contosoproxy.corp.net/proxy.pac
    ```
    
9. Cuando haya terminado de hacer los cambios, resalte la clave de usuario de Skype (carpeta raíz de Skype) y elija Descargar subárbol del menú Archivo del registro (se le solicitará confirmación, elija **Sí**).
    
10. Ahora puede cerrar el editor del registro y escribir cerrar la sesión en el cuadro de búsqueda de Windows.
    
11. Nuevamente en la pantalla de inicio de sesión, elija el usuario de **Skype**. Si todos los pasos anteriores se realizaron correctamente, el dispositivo Salas de Microsoft Teams iniciará sesión correctamente.
    
Consulte el artículo [seguridad de red](./security.md#network-security) para obtener información completa sobre los FQDN, puertos e intervalos de direcciones IP necesarios para Salas de Microsoft Teams.
  
### <a name="admin-group-management"></a>Administración del grupo de administradores

Si elige unirse a un dominio (Azure Active Directory o Active Directory), puede usar Microsoft Endpoint Manager, directiva de grupo o Administración de equipos locales para establecer un grupo de seguridad como administrador local como lo haría con un equipo Windows de su dominio. Las personas que formen parte de ese grupo de seguridad podrán introducir sus credenciales y desbloquear Configuración.
  
> [!NOTE]
> Si su dispositivo de Sala de Microsoft Teams pierde la confianza en el dominio (por ejemplo, si elimina Sala de Microsoft Teams del dominio tras haberse unido a él), no podrá autenticarse en el dispositivo ni abrir Configuración. La solución alternativa es iniciar sesión con la cuenta de administrador local. 
  
## <a name="local-accounts"></a>Cuentas locales

### <a name="microsoft-teams-rooms-local-user-account"></a>Salas de Microsoft Teams cuenta de usuario local

Salas de Teams incluye una cuenta local sin contraseñas denominada "Skype". Esta cuenta se usa para iniciar sesión en Windows para iniciar la aplicación de Salas de Teams. No se admite aplicar una contraseña a esta cuenta. Consulta [seguridad Salas de Microsoft Teams](security.md) para obtener más información.
  
### <a name="admin---local-administrator-account"></a>"Administrador": cuenta de administrador local

Salas de Microsoft Teams contraseña predeterminada se establece en "sfb". La contraseña se puede cambiar localmente a través del modo Administración o en el archivo AutoUnattend.xml (usa el Administrador de imágenes de sistema de Windows de ADK para realizar el cambio al archivo xml).
  
> [!CAUTION]
> Asegúrese de cambiar la Salas de Microsoft Teams contraseña tan pronto como sea posible. 
  
La contraseña del administrador local no se incluye como opción durante la configuración.

Puedes obtener más información sobre la cuenta de Administración en el artículo [seguridad de Salas de Microsoft Teams](security.md).
  
### <a name="machine-account"></a>Cuenta de equipo

Al igual que con cualquier dispositivo Windows, se puede cambiar el nombre del equipo haciendo clic con el botón derecho en **Configuración** \> **acerca** \> del **cambio de nombre del equipo**.
  
Si desea cambiar el nombre del equipo después de unirlo a un dominio, use [Cambiar nombre de equipo](/powershell/module/microsoft.powershell.management/rename-computer), un comando de PowerShell, seguido del nuevo nombre del equipo.
  
## <a name="related-topics"></a>Temas relacionados

[Planear Salas de Microsoft Teams](rooms-plan.md)

[Requisitos de las Salas de Microsoft Teams](requirements.md)
  
[Implementar Salas de Microsoft Teams](rooms-deploy.md)
  
[Configurar una consola de sala de Microsoft Teams](console.md)
  
[Administrar Salas de Microsoft Teams](rooms-manage.md)

[Requisitos previos para Microsoft Store para Empresas y Educación](/microsoft-store/prerequisites-microsoft-store-for-business)
