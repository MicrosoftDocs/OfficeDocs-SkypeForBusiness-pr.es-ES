---
title: Configurar puerta de enlace SIP
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Obtenga información sobre cómo configurar la puerta de enlace SIP.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: f21ce36c1c44b14b80c9ae1684a65c6bd82b7d63
ms.sourcegitcommit: 6754f2d11da0afff067f0872acf778a83fd1595e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2022
ms.locfileid: "67808881"
---
# <a name="configure-sip-gateway"></a>Configurar puerta de enlace SIP

En este artículo se explica cómo configurar puerta de enlace SIP para que su organización pueda usar dispositivos SIP compatibles con Microsoft Teams. Para averiguar qué puede hacer puerta de enlace SIP para su organización y qué hardware, software y licencias necesita su organización para ella, lea [Planear la puerta de enlace SIP](sip-gateway-plan.md).

Antes de que pueda configurar puerta de enlace SIP, haga lo siguiente:

- **Restablecer los dispositivos SIP a la configuración predeterminada de fábrica.** Usted o los usuarios de su organización deben restablecer cada dispositivo SIP que se usa con SIP Gateway a su configuración predeterminada de fábrica. Para saber cómo hacerlo, consulta las instrucciones del fabricante.

- **Abra el firewall en Microsoft 365 y Teams.** Abra el firewall de su red para el tráfico de Microsoft 365 y Teams tal y como se describe en [Office 365 URL e intervalos de direcciones IP](/microsoft-365/enterprise/urls-and-ip-address-ranges). Las reglas de firewall son necesarias solo para el tráfico saliente.

- **Asegúrese de que los dispositivos SIP no están detrás de un proxy.** Asegúrese de que el tráfico http/s omite cualquier proxy http/s corporativo.

- **Abra el puerto UDP.** Abra el puerto UDP en el intervalo de 49152 a 53247 para los intervalos IP 52.112.0.0/14 y 52.120.0.0/14.

- **Abra el puerto TCP.** Abra el puerto TCP 5061 para los intervalos IP 52.112.0.0/14 y 52.120.0.0/14.

- **Abra los siguientes puntos de conexión https (direcciones IP y DIRECCIONES URL):**

  - 13.75.175.145
  - 52.189.219.201
  - 51.124.34.164
  - 13.74.250.91
  - 13.83.55.36
  - 23.96.103.40
  - https://blobsdgapac.blob.core.windows.net
  - https://blobsdgemea.blob.core.windows.net
  - https://blobsdgnoam.blob.core.windows.net
  - https://httpblobsdgapac.blob.core.windows.net
  - https://httpblobsdgemea.blob.core.windows.net
  - https://httpblobsdgnoam.blob.core.windows.net


Las siguientes secciones describen lo que debe hacer como administrador para configurar la puerta de enlace SIP.

- [Compruebe que puerta de enlace SIP está disponible para su organización](#verify-that-sip-gateway-is-available-for-your-organization).

- [Habilite puerta de enlace SIP para los usuarios de su organización](#enable-sip-gateway-for-the-users-in-your-organization).

- [Establezca la DIRECCIÓN URL del servidor de aprovisionamiento de puerta de enlace SIP](#set-the-sip-gateway-provisioning-server-url).

En este artículo también se describe cómo:

- [Inscriba dispositivos SIP individualmente o en lotes para su comodidad](#provision-and-enroll-sip-devices-as-common-area-phones).  

- [Ver y supervisar los dispositivos SIP.](#view-and-monitor-sip-devices)

- [Habilitar la compatibilidad con una interfaz de usuario multilingüe.](#set-a-sip-devices-ui-language)

## <a name="verify-that-sip-gateway-is-available-for-your-organization"></a>Compruebe que puerta de enlace SIP está disponible para su organización

1. Inicie sesión en el [Centro de administración de Teams](https://admin.teams.microsoft.com/).

2. A la izquierda, seleccione **Dispositivos de Teams** y compruebe si la pestaña **Dispositivos SIP** está visible. Si lo está, el servicio puerta de enlace SIP está habilitado para su organización.

## <a name="enable-sip-gateway-for-the-users-in-your-organization"></a>Habilitar puerta de enlace SIP para los usuarios de su organización

Puede habilitar puerta de enlace SIP para su organización de dos maneras: mediante el Centro de administración de Teams o mediante un cmdlet de PowerShell.

### <a name="by-using-teams-admin-center"></a>Mediante el Centro de administración de Teams

Para habilitar Puerta de enlace SIP en el Centro de administración de Teams, siga estos pasos:

1. Vaya al [Centro de administración de Teams](https://admin.teams.microsoft.com/)

2. A la izquierda, en **Voz**, seleccione **Directivas de llamada**.

3. En la parte derecha, en **Administrar directivas**, seleccione la directiva de llamada adecuada asignada a los usuarios o, si es necesario, cree una nueva directiva de llamada y asígnela a los usuarios necesarios.

4. Selecciona **Administrar directivas**, selecciona una directiva y, a continuación, **Editar**.

5. Activa la configuración para **que los dispositivos SIP se puedan usar para las llamadas** y, a continuación, selecciona **Guardar**.


### <a name="by-using-powershell"></a>Mediante PowerShell

También puede habilitar SIP Gateway mediante el cmdlet [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) de PowerShell. Para habilitar a los usuarios para dispositivos SIP, seleccione una directiva y establezca el atributo en `-AllowSIPDevicesCalling` `True`. El valor predeterminado es `False`, por lo que los usuarios no podrán usar sus dispositivos SIP a menos que los habilite.

> [!NOTE]
> - La propagación de directivas puede tardar hasta 24 horas.

## <a name="set-the-sip-gateway-provisioning-server-url"></a>Establecer la dirección URL del servidor de aprovisionamiento de puerta de enlace SIP

Puede establecer la dirección URL del servidor de aprovisionamiento de puerta de enlace SIP en el servidor del Protocolo de configuración dinámica de host (DHCP). Los usuarios que trabajan de forma remota deben configurarlo manualmente.

### <a name="using-dhcp"></a>Uso de DHCP

Para cada dispositivo SIP, establezca una de las siguientes direcciones URL del servidor de aprovisionamiento de puerta de enlace SIP: 

- EMEA: `http://emea.ipp.sdg.teams.microsoft.com`
- Américas: `http://noam.ipp.sdg.teams.microsoft.com`
- APAC: `http://apac.ipp.sdg.teams.microsoft.com`

Agregue dispositivos SIP a su organización de Teams configurando la dirección URL del servidor de aprovisionamiento de puerta de enlace SIP anterior en el servidor DHCP. Para obtener más información sobre el servidor DHCP, consulta [Implementar y administrar DHCP](/training/modules/deploy-manage-dynamic-host-configuration-protocol). Además, puede utilizar la opción 42 de DHCP para especificar el servidor del Network Time Protocol (NTP) y la opción 2 de DHCP para especificar el desplazamiento desde el tiempo universal coordinado (UTC) en segundos. Los dispositivos de su organización se redirigirán al servidor de aprovisionamiento de puerta de enlace SIP. Los teléfonos SIP correctamente aprovisionados mostrarán el logotipo de Teams y un botón suave para iniciar sesión.

Asegúrese de que los dispositivos SIP están en la versión mínima de firmware compatible para la incorporación. Durante la incorporación, puerta de enlace SIP insertará la interfaz de usuario de autenticación y configuración predeterminada al dispositivo. Para averiguar la versión de firmware necesaria para dispositivos SIP, consulte [Planear la puerta de enlace SIP](sip-gateway-plan.md).

### <a name="manually"></a>Manualmente

Los usuarios que trabajan de forma remota deben configurar manualmente la dirección URL del servidor de aprovisionamiento en su dispositivo SIP mediante los siguientes pasos:

1. Abre **Configuración** en el dispositivo y obtén la dirección IP del dispositivo.

2. Abre una ventana del explorador, escribe la dirección IP del dispositivo, inicia sesión (si es necesario) y configura la dirección URL del servidor de aprovisionamiento en la utilidad web del dispositivo.

3. En **Configuración** o **Configuración avanzada** de la utilidad web, escribe la dirección URL del servidor de aprovisionamiento que se muestra arriba.

> [!NOTE]
> - Solo se pueden incorporar dispositivos SIP compatibles a la puerta de enlace SIP. 
> - Los teléfonos IP cisco deben ser flashed al firmware multiplataforma antes de que puedan ser incorporados. Para obtener información sobre cómo hacerlo, consulte [guía de conversión de firmware de Cisco](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html).
> - Para teléfonos Yealink, use la opción 66.
> - Para los teléfonos Cisco, Poly, y AudioCode, utilice la opción 160. 
> - Para los dispositivos Cisco, anexe **/$PSN.xml** al URL del servidor de aprovisionamiento.


## <a name="configure-conditional-access"></a>Configurar el acceso condicional

El acceso condicional es una característica de Azure Active Directory (Azure AD) que ayuda a garantizar que los dispositivos que tienen acceso a los recursos de Microsoft 365 se administren y protejan correctamente. Sip Gateway autentica dispositivos SIP con Azure AD, por lo que si su organización usa el acceso condicional para los dispositivos de la red corporativa, debería excluir las siguientes direcciones IP:

- Norteamérica:
    - East US: 52.170.38.140
    - Oeste de EE. UU.: 40.112.144.212
-   Región EMEA:
    - Norte de la UE: 40.112.71.149
    - Oeste de la UE: 40.113.112.67
-   Región de APAC:
    - Australia Oriental: 20.92.120.71
    - Australia Southeast: 13.73.115.90

Para obtener más información, vea [Intervalos de direcciones IP](/azure/active-directory/conditional-access/location-condition#ip-address-ranges).

## <a name="provision-and-enroll-sip-devices-as-common-area-phones"></a>Aprovisionar e inscribir dispositivos SIP como teléfonos de área comunes

> [!NOTE]
> Un dispositivo SIP debe incorporarse a la puerta de enlace SIP antes de que se pueda inscribir.

Para simplificar las tareas, puede inscribir dispositivos SIP en el centro de administración de Teams de uno en uno o en lotes. A continuación se describe cómo:

1. Inicie sesión en el [**Centro de administración de Teams**](https://admin.teams.microsoft.com).

2. Seleccione Dispositivos **SIP para** **dispositivos** >  Teams.

3. En la esquina superior derecha, selecciona **Acciones** > **Aprovisionar dispositivos** y sigue uno de estos pasos:

  - **Para aprovisionar un dispositivo:**

     a. En **Esperando activación**, selecciona **Agregar**.

     b. En el panel **Agregar direcciones MAC** , escriba la **dirección MAC** y la **ubicación** del dispositivo y, después, seleccione **Aplicar**.
     
     c. En **Esperando activación**, selecciona el dispositivo que acabas de agregar y, a continuación, selecciona **Generar código de verificación**.
     
     d. En el panel **Aprovisionar dispositivos** , en **Código de verificación**, anote el código de verificación para el dispositivo SIP.

   - **Para aprovisionar muchos dispositivos:**

     a. En **Esperando la activación**, a la derecha, seleccione **Exportar** (el icono de Microsoft Excel).
     
     b. En el panel **Aprovisionar dispositivos** , en **Cargar varias direcciones MAC**, seleccione **Descargar una plantilla**.
     
     c. Guarde **Template_Provisioning.csv** en el equipo y rellene los campos Id. y **Ubicación** de **MAC**.
    
     d. En el panel **Aprovisionar dispositivos** , seleccione **Cargar varias direcciones MAC**. 

     e. En la parte derecha del panel **Cargar direcciones MAC** , seleccione **Seleccionar un archivo** y seleccione el archivo **deTemplate_Provisioning.csv** que contiene los datos.

     F. En el panel **Aprovisionar dispositivos** , en **Espera durante la activación**, selecciona un dispositivo y, a continuación, **Generar código de verificación** para generar un código de verificación único para cada dispositivo aprovisionado. Anota el código de verificación de cada dispositivo SIP.

4. En el dispositivo SIP, marque el código de la función de inscripción seguido del código de verificación. En el dispositivo SIP, marque el código \*de característica de inscripción 55* (usado por SIP Gateway para la validación de código de verificación de una sola vez), seguido del código de verificación que se genera en el Centro de Administración de Teams para este dispositivo en particular. Por ejemplo, si el código de verificación está 123456, marque \*el número 55\*123456 para inscribir el dispositivo.

5.  En el panel **Aprovisionar dispositivos** , **en Esperando inicio de sesión**, seleccione **Sesión cerrada**.

6. En el cuadro de diálogo **Iniciar sesión como usuario** , copia o anota el código de emparejamiento del dispositivo SIP.

7. Ve a [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin)y, en **Escribir código**, escribe el código de emparejamiento del dispositivo SIP y, a continuación, selecciona **Siguiente**.

8. En la página Inicio de **sesión de** Microsoft, en el campo **Email o teléfono**, escribe la dirección de correo electrónico del dispositivo SIP y, a continuación, selecciona **Siguiente**.

9. En la página **Contraseña** , escriba la contraseña de la dirección de correo electrónico del dispositivo SIP y, a continuación, seleccione **Iniciar sesión**.

10. En la página **¿Está intentando iniciar sesión en la puerta de enlace de dispositivos SIP para Teams** ?, seleccione **Continuar**.

## <a name="how-to-sign-in-and-sign-out"></a>Cómo iniciar y cerrar sesión

Solo se admite el inicio de sesión local en los dispositivos personales de los usuarios. Para cerrar la sesión de un dispositivo desde el centro de Administración, sigue estos pasos:

1. Inicie sesión en el [**Centro de administración de Teams**](https://admin.teams.microsoft.com).

2. Seleccione Dispositivos **SIP para** **dispositivos** >  Teams.

3. A la derecha, seleccione un dispositivo SIP y, a continuación, seleccione **Cerrar sesión**.


### <a name="user-pairing-and-sign-in"></a>Emparejamiento e inicio de sesión de usuario

Para emparejar un dispositivo SIP después de que el usuario se autentique con credenciales corporativas, un usuario debe:

1. Presione **Iniciar sesión en** el teléfono SIP para mostrar la dirección URL de autenticación y el código de emparejamiento. El código de emparejamiento es sensible al tiempo. Si expira, el usuario debe presionar **Atrás** en el teléfono e iniciar el proceso de inicio de sesión de nuevo.

2. Vaya a la dirección URL de autenticación en el explorador móvil o de escritorio del usuario y use credenciales corporativas para iniciar sesión.

3. Introduzca el código de emparejamiento que se muestra en el teléfono SIP en la aplicación de autenticación web para emparejar el teléfono SIP con la cuenta del usuario. En un inicio de sesión correcto, que puede tardar un rato, el teléfono SIP mostrará el número de teléfono y el nombre de usuario, si el dispositivo lo admite.

> [!NOTE]
> La ubicación del dispositivo que se muestra en la aplicación de autenticación web de Azure Active Directory es el centro de datos de puerta de enlace SIP al que está conectado el dispositivo. Los teléfonos SIP en el ámbito no son compatibles con OAuth, por lo que puerta de enlace SIP autentica al usuario a través de la aplicación de autenticación web y, a continuación, empareja el dispositivo con las credenciales del usuario. Obtenga más información aquí: [Plataforma de identidad de Microsoft y el flujo de autorización de dispositivo de OAuth 2.0](/azure/active-directory/develop/v2-oauth2-device-code).

### <a name="sign-out"></a>Cerrar sesión

Para cerrar la sesión, un usuario del dispositivo puede:

- Presione **Cerrar sesión** en el dispositivo SIP y siga los pasos descritos en el dispositivo. 

Para cerrar la sesión de un dispositivo en el Centro de administración de Teams:

1. Inicie sesión en el [**Centro de administración de Teams**](https://admin.teams.microsoft.com).

2. Seleccione Dispositivos **SIP para** **dispositivos** >  Teams.

3. A la derecha, en el panel **dispositivos SIP** , seleccione el dispositivo.

4. En el **panel Detalles** del dispositivo, seleccione la pestaña **Detalles** y, en la esquina superior derecha del menú **Acciones** , seleccione **Cerrar sesión**. 

## <a name="view-and-monitor-sip-devices"></a>Ver y supervisar dispositivos SIP

Puede ver y supervisar el inventario de dispositivos SIP en el Centro de administración de Teams después de que los usuarios de los dispositivos inicien sesión al menos una vez. A continuación se describe cómo:

1. Inicie sesión en el [Centro de administración de Teams](https://admin.teams.microsoft.com/).

2. Seleccione Dispositivos **SIP para** **dispositivos** >  Teams. Todos los dispositivos SIP con sesión iniciada aparecen a la derecha.

## <a name="restart-a-sip-device"></a>Reiniciar un dispositivo SIP

1. Inicie sesión en el [Centro de administración de Teams](https://admin.teams.microsoft.com).

2. Seleccione Dispositivos **SIP para** **dispositivos** >  Teams. 

3. A la derecha, selecciona el dispositivo SIP que quieras reiniciar y, a continuación, selecciona **Reiniciar**.


> [!NOTE]
> - La eliminación de un dispositivo SIP de su inquilino no está disponible actualmente en el Centro de administración de Teams. 
> - La ejecución de comandos depende de la disponibilidad del dispositivo y puede que no coincida con el estado de ejecución que se muestra en el Centro de administración de Teams. Si intenta habilitar la puerta de enlace SIP en un dispositivo que no la admite, el comando no se ejecutará.

## <a name="sync-policy-changes-to-sip-devices-to-enforce-policies"></a>Sincronizar cambios de directivas en dispositivos SIP para aplicar directivas

Las directivas y los detalles del usuario se recuperarán en los dispositivos SIP cuando los usuarios inicien sesión. Cualquier cambio de directiva posterior para los usuarios con sesión iniciada se sincronizará con el dispositivo en el plazo de una hora. Los dispositivos deben tener su registro actualizado periódicamente con la puerta de enlace SIP. Los teléfonos SIP dependen de la redirección de llamadas, por lo que el administrador debe establecer el `AllowCallRedirect` atributo en `Set-CsTeamsCallingPolicy` `Enabled`.


## <a name="set-a-sip-devices-ui-language"></a>Establecer el idioma de la interfaz de usuario de un dispositivo SIP

Un dispositivo SIP normalmente puede mostrar información en muchos idiomas. Configurar el idioma de la interfaz de usuario afecta a su interfaz, incluidas las teclas temporales y los mensajes del sistema de inicio y cierre de sesión. La configuración del idioma de la interfaz de usuario se realiza en el servidor de aprovisionamiento, mediante el servidor DHCP o manualmente anexando una cadena de código en la dirección URL, como en los ejemplos siguientes.

Cómo configurar alemán para teléfonos Polycom, AudioCodes y Yealink:
- `http://emea.ipp.sdg.teams.microsoft.com/lang_de`

Cómo establecer el japonés para los Teléfonos Cisco:
- `http://emea.ipp.sdg.teams.microsoft.com/lang_ja/$PSN.xml` 


### <a name="supported-languages"></a>Idiomas admitidos

|Nombre del idioma|Código de idioma]
|-------------|-------------|
|Inglés (predeterminado)|en       |
|Español      |es           |
|Japonés     |ja           |
|Alemán       |de           |
|Francés       |Fr           |
|Portugués   |Pt           |

> [!Note]
> - El japonés no es compatible con Yealink y parcialmente compatible con Polycom VVX.
> - El sistema se usa de forma predeterminada en inglés si el idioma seleccionado no es compatible con el punto de conexión SIP.
> - Cuando el parámetro **lang_xx** no se establece a través de la dirección URL de aprovisionamiento, se usa el inglés como idioma predeterminado.
> - Si **el inicio de sesión para realizar una llamada de emergencia** no está traducido a otros idiomas, solo se mostrará una versión abreviada en inglés en el **inicio de sesión de prensa** en los siguientes modelos de teléfono IP debido a las limitaciones de tamaño de pantalla:
>   - Poly VVX 150, VVX 201
>   - Cisco CP-6821, CP-7811, CP-7821, CP-7841, CP-7861
>   - La etiqueta de clave temporal de correo de voz está **codificada de forma** impresa con texto vm en todos los idiomas para Poly VVX debido a una limitación de la longitud de la cadena.

## <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams y IPv6

SIP Gateway solo admite IPv4. El servicio y el cliente de Microsoft Teams son compatibles tanto con IPv4 como con IPv6. Si desea controlar las comunicaciones con Microsoft Teams, use los intervalos de direcciones IP de [las direcciones URL e intervalos de direcciones IP de Microsoft 365](/microsoft-365/enterprise/urls-and-ip-address-ranges).

## <a name="emergency-calling"></a>Llamadas de emergencia

Sip Gateway admite llamadas de emergencia dinámicas (E911 dinámicas) para dispositivos SIP compatibles que comparten atributos de red a través de la cable. Estos atributos se aprovisionan en el Centro de administración de Teams y pueden ser una combinación de IP local y longitud de subred, o id. de chasis y número de puerto de red. Para los dispositivos que no comparten atributos de ubicación, o si la ubicación no se resuelve dinámicamente por cualquier motivo, SIP Gateway seguirá admitiendo las llamadas de emergencia basadas en direcciones registradas. Actualmente, las direcciones registradas no son compatibles con los escenarios de enrutamiento directo. Para obtener más información sobre las llamadas de emergencia, consulte [Planear y administrar las llamadas de emergencia](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing).

## <a name="report-problems-to-microsoft"></a>Informar de problemas a Microsoft

Para informar de problemas, ponte en contacto con [Soporte técnico de Microsoft](https://support.microsoft.com).
