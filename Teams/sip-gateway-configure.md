---
title: Configurar SIP Gateway
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
description: Obtenga información sobre cómo configurar SIP Gateway.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: a4548ab9abfd96b3945c19c07e08baf1ede05983
ms.sourcegitcommit: 1e83f2c1ed12bcb611eb4eb0a5f1f58496c63147
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/13/2021
ms.locfileid: "61426112"
---
# <a name="configure-sip-gateway"></a>Configurar SIP Gateway

En este artículo se explica cómo configurar SIP Gateway para que su organización pueda usar dispositivos SIP compatibles con Microsoft Teams. Para saber qué puede hacer SIP Gateway para su organización y qué hardware, software y licencias necesita su organización para ella, lea [Plan para SIP Gateway.](sip-gateway-plan.md)

Antes de configurar SIP Gateway, haga lo siguiente:

- **Restablecer los dispositivos SIP a la configuración predeterminada de fábrica.** Usted o los usuarios de su organización deben restablecer cada dispositivo SIP que se usa con SIP Gateway a su configuración predeterminada de fábrica. Para averiguar cómo hacerlo, consulta las instrucciones del fabricante.

- **Abra el firewall para Microsoft 365 y Teams.** Abra el firewall de su red para Microsoft 365 y Teams tráfico como se describe en Office 365 direcciones URL e [intervalos de direcciones IP](/microsoft-365/enterprise/urls-and-ip-address-ranges).

- **Asegúrese de que los dispositivos SIP no están detrás de un proxy.** Asegúrese de que el tráfico http/s omite cualquier proxy http/s corporativo.

- **Abra el puerto UDP.** Abra el puerto UDP en el rango 49152 a 53247.

- **Abra el puerto TCP.** Abra el puerto TCP 5061 para rangos IP 52.112.0.0/14 a 52.120.0.0/14.

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



En las secciones siguientes se describe lo que debe hacer como administrador para configurar SIP Gateway.

- [Compruebe que SIP Gateway está disponible para su organización.](#verify-that-sip-gateway-is-available-for-your-organization)

- [Habilite SIP Gateway para los usuarios de su organización.](#enable-sip-gateway-for-the-users-in-your-organization)

- [Establezca la dirección URL del servidor de aprovisionamiento de SIP Gateway.](#set-the-sip-gateway-provisioning-server-url)

En este artículo también se describe cómo:

- [Inscriba dispositivos SIP individualmente o en lotes para su comodidad.](#provision-and-enroll-sip-devices-as-common-area-phones)  


- [Ver y supervisar los dispositivos SIP.](#view-and-monitor-sip-devices)

- [Habilite la compatibilidad con una interfaz de usuario en varios idiomas.](#set-a-sip-devices-ui-language)

## <a name="verify-that-sip-gateway-is-available-for-your-organization"></a>Comprobar que SIP Gateway está disponible para su organización

1. Inicie sesión en el [Teams de administración](https://admin-teams.microsoft.com/).

2. A la izquierda, seleccione **Teams dispositivos** y vea si la pestaña Dispositivos **SIP** está visible. Si es así, el servicio SIP Gateway está habilitado para su organización.

## <a name="enable-sip-gateway-for-the-users-in-your-organization"></a>Habilitar SIP Gateway para los usuarios de su organización

Puede habilitar SIP Gateway para su organización de dos maneras: mediante el centro de administración de Teams o mediante un cmdlet de PowerShell.

### <a name="by-using-teams-admin-center"></a>Al usar Teams de administración

Para habilitar SIP Gateway en el Teams de administración, siga estos pasos:

1. Ir al Centro [Teams administración](https://admin.teams.microsoft.com/)

2. A la izquierda, en **Voz,** seleccione **Directivas de llamadas.**

3. A la derecha, en **Administrar directivas,** seleccione la directiva de llamadas adecuada asignada a los usuarios o, si es necesario, cree una nueva directiva de llamadas y asígnela a los usuarios necesarios.

4. Seleccione **Administrar directivas,** seleccione una directiva y, a continuación, **seleccione Editar.**

5. Activar la configuración para dispositivos **SIP se puede usar para** llamadas y, a continuación, seleccione **Guardar.**


### <a name="by-using-powershell"></a>Con PowerShell

También puede habilitar SIP Gateway con el cmdlet [Set-CsTeamsCallingPolicy de](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) PowerShell. Para habilitar usuarios para dispositivos SIP, seleccione una directiva y establezca el `-AllowSIPDevicesCalling` atributo en `True` . El valor predeterminado es , por lo que los usuarios no podrán usar sus dispositivos SIP a menos `False` que los habilite.


> [!NOTE]
> - La propagación de directivas puede tardar hasta 24 horas.

## <a name="set-the-sip-gateway-provisioning-server-url"></a>Establecer la dirección URL del servidor de aprovisionamiento de SIP Gateway

Puede establecer la dirección URL del servidor de aprovisionamiento de SIP Gateway en el servidor de protocolo de configuración dinámica de host (DHCP). Los usuarios que trabajan de forma remota deben configurarlo manualmente.

### <a name="using-dhcp"></a>Usar DHCP

Para cada dispositivo SIP, establezca una de las siguientes direcciones URL del servidor de aprovisionamiento de SIP Gateway: 

- EMEA: `http://emea.ipp.sdg.teams.microsoft.com`
- América: `http://noam.ipp.sdg.teams.microsoft.com`
- APAC: `http://apac.ipp.sdg.teams.microsoft.com`

Agregue dispositivos SIP a su Teams organización configurando la dirección URL del servidor de aprovisionamiento de SIP Gateway anterior en el servidor DHCP. Para obtener más información sobre el servidor DHCP, vea [Implementar y administrar DHCP.](/learn/modules/deploy-manage-dynamic-host-configuration-protocol) Además, puede usar la opción 42 de DHCP para especificar el servidor de Protocolo de hora de red (NTP) y la opción DHCP 2 para especificar el desplazamiento de la hora universal coordinada (UTC) en cuestión de segundos. Los dispositivos de su organización se enrutarán al servidor de aprovisionamiento de SIP Gateway. Los teléfonos SIP aprovisionados correctamente mostrarán el Teams y un botón suave para iniciar sesión.

Asegúrese de que los dispositivos SIP están en la versión de firmware mínima compatible para la incorporación. Durante la incorporación, SIP Gateway insertará la interfaz de usuario predeterminada de configuración y autenticación en el dispositivo. Para obtener información sobre la versión de firmware necesaria para dispositivos SIP, vea [Plan para SIP Gateway.](sip-gateway-plan.md)

### <a name="manually"></a>Manualmente

Los usuarios que trabajan de forma remota deben configurar manualmente la dirección URL del servidor de aprovisionamiento en su dispositivo SIP siguiendo los pasos siguientes:

1. Abra **Configuración** en el dispositivo y obtenga la dirección IP del dispositivo.

2. Abra una ventana del explorador, escriba la dirección IP del dispositivo, inicie sesión (si es necesario) y configure la dirección URL del servidor de aprovisionamiento en la utilidad web del dispositivo.

3. En **Configuración** o **Configuración avanzada** en la utilidad web, escriba la dirección URL del servidor de aprovisionamiento que se muestra anteriormente.

> [!NOTE]
> - Solo los dispositivos SIP compatibles se pueden incorporar a SIP Gateway. 
> - Los teléfonos IP de Cisco deben parpadear en el firmware multiplataforma antes de que se puedan incorporar. Para obtener más información, consulte [Guía de conversión de firmware de Cisco.](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html)
> - Para teléfonos Yealink, use la opción 66.
> - Para teléfonos Cisco, Poly y AudioCode, use la opción 160. 
> - Para dispositivos Cisco, anexe **/$PSN.xml** a la dirección URL del servidor de aprovisionamiento.


## <a name="configure-conditional-access"></a>Configurar el acceso condicional

Acceso condicional es una característica Azure Active Directory (Azure AD) que ayuda a garantizar que los dispositivos que tienen acceso a sus Microsoft 365 recursos se administran y protegen correctamente. SIP Gateway autentica los dispositivos SIP con Azure AD, por lo que si su organización usa acceso condicional para dispositivos de la red corporativa, debe excluir las siguientes direcciones IP:

- Norteamérica:
    - Este de EE. UU.: 52.170.38.140
    - Oeste de EE. UU.: 40.112.144.212
-   Región EMEA:
    - Norte de la UE: 40.112.71.149
    - Oeste de la UE: 40.113.112.67
-   Región APAC:
    - Australia Este: 20.92.120.71
    - Australia Sureste: 13.73.115.90

Para obtener más información, vea [Intervalos de direcciones IP.](/azure/active-directory/conditional-access/location-condition#ip-address-ranges)


## <a name="provision-and-enroll-sip-devices-as-common-area-phones"></a>Aprovisionar e inscribir dispositivos SIP como teléfonos de área comunes
> [!NOTE]
> Un dispositivo SIP debe incorporarse a SIP Gateway para poder inscribirse.

Para simplificar las tareas, puede inscribir dispositivos SIP en el Teams de administración de uno en uno o en lotes. A continuación se describe cómo:

1. Inicie sesión en el [**Teams de administración.**](https://admin.teams.microsoft.com)

2. Seleccione **Teams dispositivos**  >  **SIP**.

3. En la esquina superior derecha, seleccione **Dispositivos**  >  **de aprovisionamiento de acciones** y siga uno de estos pasos:

  - **Para aprovisionar un dispositivo:**

     a. En **Esperando la activación,** seleccione **Agregar**.

     b. En el **panel Agregar direcciones MAC,** escriba la dirección **MAC** y **la ubicación** del dispositivo y, a continuación, **seleccione Aplicar.**
     
     c. En **Esperando la activación,** seleccione el dispositivo que acaba de agregar y, a continuación, **seleccione Generar código de verificación.**
     
     d. En el **panel Aprovisionar dispositivos,** en **Código de verificación,** anote el código de verificación para el dispositivo SIP.

   - **Para aprovisionar muchos dispositivos:**

     a. En **Esperando la activación,** a la derecha, **seleccione Exportar** (Microsoft Excel icono).
     
     b. En el **panel Aprovisionar dispositivos,** en **Upload varias direcciones MAC,** seleccione **Descargar una plantilla.**
     
     c. Guarde **Template_Provisioning.csv** en el equipo y rellene los campos **Id. y** **Ubicación** de MAC.
    
     d. En el **panel Aprovisionar dispositivos,** **seleccione Upload varias direcciones MAC.** 

     e. A la derecha en el panel Upload  **direcciones MAC,** seleccione Seleccionar un archivo y seleccione elTemplate_Provisioning.csv **que** contiene los datos.

     f. En el **panel Aprovisionar** dispositivos, en Esperando  la **activación,** seleccione un dispositivo y, a continuación, seleccione Generar código de verificación para generar un código de verificación único para cada dispositivo aprovisionado. Anote el código de verificación de cada dispositivo SIP.

4. En el dispositivo SIP, marque el código de característica de inscripción seguido del código de verificación. En el dispositivo SIP, marque el código de característica de inscripción 55* (usado por SIP Gateway para la validación de código de verificación único de inscripción), seguido del código de verificación que se genera en el Centro de administración de Teams para este dispositivo \* en particular. Por ejemplo, si el código de verificación está 123456, marque \* 55 123456 para inscribir el \* dispositivo.

5.  En el **panel Aprovisionar dispositivos,** en **Esperando inicio de sesión,** seleccione **Cerrar sesión.**

6. En el **cuadro de diálogo Iniciar sesión en un** usuario, copie o anote el código de emparejamiento del dispositivo SIP.

7. Vaya a y, en Entrar código, escriba el código de emparejamiento del dispositivo SIP y, a [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin) continuación, seleccione **Siguiente.** 

8. En la página Inicio de  **sesión de** Microsoft, en el campo Correo electrónico o teléfono, escriba la dirección de correo electrónico del dispositivo SIP y, a continuación, **seleccione Siguiente.**

9. En la **página Contraseña,** escriba la contraseña de la dirección de correo electrónico del dispositivo SIP y, a continuación, **seleccione Iniciar sesión.**

10. En la **página ¿Está intentando iniciar sesión** en Teams puerta de enlace de dispositivos SIP?, seleccione **Continuar**.

## <a name="how-to-sign-in-and-sign-out"></a>Cómo iniciar sesión y cerrar sesión

Solo se admite el inicio de sesión local para los dispositivos personales de los usuarios. Para cerrar la sesión de un dispositivo desde el Centro de administración, siga estos pasos:

1. Inicie sesión en el [**Teams de administración.**](https://admin.teams.microsoft.com)

2. Seleccione **Teams dispositivos**  >  **SIP**.

3. A la derecha, seleccione un dispositivo SIP y, a continuación, seleccione **Cerrar sesión.**


### <a name="user-pairing-and-sign-in"></a>Emparejamiento de usuarios e inicio de sesión

Para emparejar un dispositivo SIP después de que el usuario se autentique con credenciales corporativas, un usuario debe:

1. Presione **Iniciar sesión en el** teléfono SIP para mostrar la dirección URL de autenticación y el código de emparejamiento. El código de emparejamiento es sensible al tiempo. Si expira, el usuario debe presionar **Atrás** en el teléfono e iniciar de nuevo el proceso de inicio de sesión.

2. Vaya a la dirección URL de autenticación en el explorador móvil o de escritorio del usuario y use credenciales corporativas para iniciar sesión.

3. Escriba el código de emparejamiento que se muestra en el teléfono SIP en la aplicación de autenticación web para emparejar el teléfono SIP con la cuenta del usuario. En un inicio de sesión correcto, que puede tardar un tiempo, el teléfono SIP mostrará el número de teléfono y el nombre de usuario, si el dispositivo lo admite.

> [!NOTE]
> La ubicación del dispositivo que se muestra en la Azure Active Directory de autenticación web es el centro de datos de SIP Gateway al que está conectado el dispositivo. Los teléfonos SIP en el ámbito no son compatibles con OAuth, por lo que SIP Gateway autentica al usuario a través de la aplicación de autenticación web y, a continuación, empareja el dispositivo con las credenciales del usuario. Más información aquí: Plataforma de identidad de Microsoft y el flujo de concesión de autorización de dispositivo [de OAuth 2.0.](/azure/active-directory/develop/v2-oauth2-device-code)

### <a name="sign-out"></a>Cerrar sesión

Para cerrar la sesión, un usuario del dispositivo puede:

- Presione **Cerrar sesión en** el dispositivo SIP y siga los pasos descritos en el dispositivo. 

Para cerrar la sesión de un dispositivo en el Teams de administración:

1. Inicie sesión en el [**Teams de administración.**](https://admin.teams.microsoft.com)

2. Seleccione **Teams dispositivos**  >  **SIP**.

3. A la derecha, en el panel **Dispositivos SIP,** seleccione el dispositivo.

4. En el panel Detalles **del**  dispositivo, seleccione la pestaña Detalles  y, en la esquina superior derecha del menú Acciones, seleccione Cerrar **sesión.** 


## <a name="view-and-monitor-sip-devices"></a>Ver y supervisar dispositivos SIP

Puede ver y supervisar el inventario de dispositivos SIP en el Teams de administración después de que los usuarios de los dispositivos inicien sesión al menos una vez. A continuación se describe cómo:

1. Inicie sesión en el [Teams de administración.](https://admin.teams.microsoft.com/)

2. Seleccione **Teams dispositivos**  >  **SIP**. Todos los dispositivos SIP que han iniciado sesión se muestran a la derecha.

## <a name="restart-a-sip-device"></a>Reiniciar un dispositivo SIP

1. Inicie sesión en el [Teams de administración.](https://admin.teams.microsoft.com)

2. Seleccione **Teams dispositivos**  >  **SIP**. 

3. A la derecha, seleccione el dispositivo SIP que desea reiniciar y, a continuación, **seleccione Reiniciar.**

## <a name="sync-policy-changes-to-sip-devices-to-enforce-policies"></a>Sincronizar cambios de directiva en dispositivos SIP para aplicar directivas

Los detalles de usuario y las directivas se capturarán en dispositivos SIP cuando los usuarios inicien sesión. Los cambios de directiva posteriormente para los usuarios que han iniciado sesión se sincronizarán con el dispositivo en un plazo de una hora. Los dispositivos deben tener su registro actualizado con sip gateway periódicamente. Los teléfonos SIP dependen de la redirección de llamadas, por lo que el administrador debe `AllowCallRedirect` establecer el atributo en `Set-CsTeamsCallingPolicy` `Enabled` .


## <a name="set-a-sip-devices-ui-language"></a>Establecer el idioma de la interfaz de usuario de un dispositivo SIP

Un dispositivo SIP normalmente puede mostrar información en muchos idiomas. Establecer el idioma de la interfaz de usuario afecta a su interfaz, incluidas las teclas de teclado y los mensajes del sistema de inicio de sesión o de salida. La configuración del idioma de la interfaz de usuario se realiza en el servidor de aprovisionamiento, con el servidor DHCP o manualmente anexando una cadena de código en la dirección URL como en los ejemplos siguientes.

Cómo configurar el alemán para teléfonos Polycom, AudioCodes y Yealink:
- `http://emea.ipp.sdg.teams.microsoft.com/lang_de`

Cómo configurar el japonés para teléfonos Cisco:
- `http://emea.ipp.sdg.teams.microsoft.com/lang_ja/$PSN.xml` 


### <a name="supported-languages"></a>Idiomas admitidos

|Nombre de idioma|Código de idioma]
|-------------|-------------|
|Inglés (predeterminado)|en       |
|Español      |es           |
|Japonés     |ja           |
|Alemán       |de           |
|Francés       |fr           |
|Portugués   |pt           |

> [!Note]
> - El japonés no es compatible con Yealink y es parcialmente compatible con Polycom VVX.
> - El sistema es predeterminado en inglés si el punto de conexión SIP no admite el idioma seleccionado.
> - Cuando el **lang_xx** no se establece a través de la dirección URL de aprovisionamiento, el inglés se usa como el idioma predeterminado.
> - Si  iniciar sesión para realizar una llamada de emergencia no se traduce a otros idiomas,  solo se mostrará una versión abreviada en inglés al presionar Iniciar sesión en los siguientes modelos de teléfono IP debido a las limitaciones de tamaño de pantalla:
>   - Poly VVX 150, VVX 201
>   - Cisco CP-6821, CP-7811, CP-7821, CP-7841, CP-7861
>   - La etiqueta de la clave temporal de correo de voz se codifica con texto **de máquina virtual** en todos los idiomas para Poly VVX debido a una limitación de la longitud de cadena.

## <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams iPv6

SIP Gateway solo admite IPv4. Microsoft Teams y el cliente admiten IPv4 e IPv6. Si desea controlar las comunicaciones Microsoft Teams, use los intervalos de direcciones IP en Microsoft 365 direcciones URL e [intervalos de direcciones IP.](/microsoft-365/enterprise/urls-and-ip-address-ranges)

## <a name="emergency-calling"></a>Llamadas de emergencia

SIP Gateway solo admite direcciones de emergencia estáticas (también denominadas direcciones de emergencia registradas). Actualmente, las direcciones registradas no son compatibles con escenarios de enrutamiento directo. Para obtener más información sobre las llamadas de emergencia, vea [Planear y administrar llamadas de emergencia.](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)

## <a name="report-problems-to-microsoft"></a>Informar de problemas a Microsoft

Para informar de problemas, póngase en contacto con [el soporte técnico de Microsoft.](https://support.microsoft.com)
