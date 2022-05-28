---
title: seguridad de Salas de Microsoft Teams
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: sohailta
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: Obtén información sobre cómo proteger tus dispositivos Salas de Microsoft Teams.
ms.openlocfilehash: 135e286ce255f097dc3751bc509c05fc94f2ffb2
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2022
ms.locfileid: "65761102"
---
# <a name="microsoft-teams-rooms-security"></a>seguridad de Salas de Microsoft Teams

Microsoft trabaja con nuestros asociados para ofrecer una solución segura y que no requiera acciones adicionales para proteger Salas de Microsoft Teams. En este artículo se describen muchas de las características de seguridad que se encuentran en Salas de Teams.

> [!NOTE]
> Salas de Microsoft Teams no debe tratarse como una estación de trabajo típica de usuario final. No solo son muy diferentes los casos de uso, sino que los perfiles de seguridad predeterminados también son muy diferentes.
> Este artículo se aplica a Salas de Microsoft Teams dispositivos que se ejecutan en Windows.

Los datos limitados de los usuarios finales se almacenan en Salas de Teams. Los datos del usuario final pueden almacenarse en los archivos de registro solo para solucionar problemas y soporte técnico. En ningún momento un asistente a una reunión puede usar Salas de Teams copiar archivos en el disco duro o iniciar sesión como ellos mismos. No se transfieren datos del usuario final al dispositivo Salas de Microsoft Teams ni se puede acceder a ellos.

Aunque los usuarios finales no pueden colocar archivos en un Salas de Teams disco duro, Microsoft Defender sigue estando habilitado. Salas de Teams rendimiento se prueba con Microsoft Defender. Deshabilitar este software o agregar software de seguridad de extremo puede provocar resultados impredecibles y una posible degradación del sistema.

## <a name="hardware-security"></a>Seguridad de hardware

En un entorno Salas de Teams, hay un módulo de proceso central que ejecuta Windows 10 IoT Enterprise edición. Cada módulo de computación certificado debe tener una solución de montaje seguro, una ranura de bloqueo de seguridad (por ejemplo, Bloqueo Kensington) y medidas de seguridad de acceso al puerto de E/S para evitar la conexión de dispositivos no autorizados. También puedes deshabilitar puertos específicos a través de la configuración de Unified Extensible Firmware Interface (UEFI).

Cada módulo de proceso certificado debe incluirse con la tecnología compatible con Trusted Platform Module (TPM) 2.0 habilitada de forma predeterminada. TPM se usa para cifrar la información de inicio de sesión de la cuenta de recursos de Salas de Teams.

El arranque seguro está habilitado de manera predeterminada. El arranque seguro es un estándar de seguridad desarrollado por miembros del sector de equipos para ayudar a garantizar que un dispositivo arranque usando solo software que sea de confianza para el fabricante de equipos originales (OEM). Cuando se inicia el equipo, el firmware comprueba la firma de cada componente de software de arranque, incluidos los controladores de firmware UEFI (también conocidos como ROM de opción), las aplicaciones EFI y el sistema operativo. Si las firmas son válidas, el equipo arranca y el firmware da control al sistema operativo. Para obtener más información, consulta [Arranque seguro](/windows-hardware/design/device-experiences/oem-secure-boot).

El acceso a la configuración de la UEFI solo es posible conectando un teclado y un mouse físicos. Esto impide acceder a la UEFI a través de la Salas de Teams consola táctil, así como a cualquier otra pantalla táctil conectada a Salas de Teams.

La protección de acceso directo a memoria (DMA) del kernel es una configuración de Windows 10 habilitada en Salas de Teams. Con esta característica, el sistema operativo y el firmware del sistema protegen el sistema contra ataques DMA malintencionados e imprevistos para todos los dispositivos compatibles con DMA:

- Durante el proceso de arranque.

- Contra la DMA malintencionada por dispositivos conectados a puertos compatibles con DMA internos o externos de fácil acceso, como ranuras M.2 PCIe y Thunderbolt 3, durante el tiempo de ejecución del sistema operativo.

Salas de Teams también habilita la integridad del código protegido por hipervisor (HVCI). Una de las características proporcionadas por HVCI es Credential Guard. Credential Guard ofrece las siguientes ventajas:

- **Seguridad de hardware** NTLM, Kerberos y Credential Manager aprovechan las características de seguridad de la plataforma, como el arranque seguro y la virtualización, para proteger las credenciales.

- **La seguridad basada en virtualización** Windows ntlm y kerberos credenciales derivadas y otros secretos se ejecutan en un entorno protegido que está aislado del sistema operativo en ejecución.

- **Mejor protección contra amenazas persistentes avanzadas** Cuando las credenciales derivadas de Credential Manager, NTLM y Kerberos están protegidas mediante seguridad basada en virtualización, se bloquean las técnicas y herramientas de ataques de robo de credenciales usadas en muchos ataques dirigidos. El malware que se ejecuta en el sistema operativo con privilegios administrativos no puede extraer secretos protegidos por seguridad basada en virtualización.

## <a name="software-security"></a>Seguridad del software

Después de que Microsoft Windows arranque, Salas de Teams inicia sesión automáticamente en una cuenta de usuario Windows local denominada Skype. La cuenta Skype no tiene contraseña. Para proteger la sesión de Skype cuenta, se realizan los pasos siguientes.

> [!IMPORTANT]
> No cambies la contraseña ni edites la cuenta de usuario Skype local. Si lo hace, puede impedir que Salas de Teams inicien sesión automáticamente.

La aplicación Salas de Microsoft Teams se ejecuta con la característica acceso asignado que se encuentra en Windows 10 1903 y posteriores. Acceso asignado es una característica de Windows 10 que limita los puntos de entrada de la aplicación expuestos al usuario. Esto es lo que permite el modo de pantalla completa de una sola aplicación. Con la Selector shell, Salas de Teams se configura como un dispositivo de quiosco que ejecuta una aplicación de escritorio Windows como la interfaz de usuario. La aplicación Salas de Microsoft Teams reemplaza el shell predeterminado (explorer.exe) que normalmente se ejecuta cuando un usuario inicia sesión. En otras palabras, el shell del Explorador tradicional no se inicia en absoluto. Esto reduce enormemente la superficie de vulnerabilidad Salas de Microsoft Teams dentro de Windows. Para obtener más información, consulta [Configurar quioscos y signos digitales en Windows ediciones de escritorio](/windows/configuration/kiosk-methods).

Si decide ejecutar un análisis de seguridad o un punto de referencia del Centro de seguridad de Internet (CIS) en Salas de Teams, el examen solo puede ejecutarse en el contexto de una cuenta de administrador local, ya que la cuenta de usuario Skype no admite aplicaciones en ejecución que no sean la aplicación Salas de Teams. Muchas de las características de seguridad aplicadas al contexto de usuario Skype no se aplican a otros usuarios locales y, como resultado, estos exámenes de seguridad no surface the full security lockdown applied to the Skype account. Por lo tanto, no se recomienda ejecutar un análisis local en Salas de Teams. Sin embargo, puede ejecutar pruebas de penetración externa si así lo desea. Por este motivo, le recomendamos que realice pruebas de penetración externa en dispositivos Salas de Teams en lugar de ejecutar digitalizaciones locales.

Además, las directivas de bloqueo se aplican para limitar el uso de características no administrativas. Se habilita un filtro de teclado para interceptar y bloquear combinaciones de teclado potencialmente inseguras que no están cubiertas por las directivas de acceso asignado. Solo los usuarios con derechos administrativos locales o de dominio pueden iniciar sesión en Windows para administrar Salas de Teams. Estas y otras directivas aplicadas a Windows en dispositivos Salas de Microsoft Teams se evalúan y prueban continuamente durante el ciclo de vida del producto.

## <a name="account-security"></a>Seguridad de la cuenta

Salas de Teams dispositivos incluyen una cuenta administrativa denominada "Administración" con una contraseña predeterminada. Le recomendamos que cambie la contraseña predeterminada tan pronto como sea posible después de completar la configuración.

La cuenta de Administración no es necesaria para el correcto funcionamiento de Salas de Teams dispositivos y se puede cambiar el nombre o incluso eliminarse. Sin embargo, antes de eliminar la cuenta de Administración, asegúrate de configurar una cuenta de administrador local alternativa configurada antes de quitar la que viene con dispositivos Salas de Teams. Para obtener más información sobre cómo cambiar una contraseña de una cuenta de Windows local mediante herramientas de Windows integradas o PowerShell, vea lo siguiente:

- [Cambiar o restablecer la contraseña de Windows](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1#example-2--change-the-password-on-an-account)

También puede importar cuentas de dominio al grupo administrador de Windows local. Puede hacerlo con cuentas de Azure AD mediante Intune. Para obtener más información, consulta [Csp de directivas: Grupos restringidos.](/windows/client-management/mdm/policy-csp-restrictedgroups)

> [!NOTE]
> Si usas consolas Crestron, asegúrate de actualizar también la contraseña de Administración en la consola, así como en el módulo de cálculo. Para obtener más información, ponte en contacto con Crestron.

> [!CAUTION]
> Si elimina o deshabilita la cuenta de Administración antes de conceder permisos de administrador local a otra cuenta local o de dominio, puede perder la capacidad de administrar el dispositivo Salas de Teams. Si esto sucede, tendrás que restablecer el dispositivo a su configuración original y completar el proceso de configuración de nuevo.

No conceda permisos de administrador local a la cuenta de usuario de Skype.

Windows Diseñador de configuración se puede usar para crear Windows 10 paquetes de aprovisionamiento. Además de cambiar la contraseña de Administración local, también puede hacer cosas como cambiar el nombre del equipo e inscribirse en Azure Active Directory. Para obtener más información sobre cómo crear una Windows paquete de aprovisionamiento del Diseñador de configuración, consulta [Aprovisionamiento de paquetes para Windows 10](/windows/configuration/provisioning-packages/provisioning-packages).

Debe crear una cuenta de recursos para cada dispositivo Salas de Teams para que pueda iniciar sesión en Teams. No puede usar la autenticación multifactor o de dos factores con esta cuenta. Requerir un segundo factor impediría que la cuenta pudiera iniciar sesión automáticamente en la aplicación Salas de Teams después de reiniciar. Sin embargo, puede habilitar la autenticación moderna para mayor seguridad para esta cuenta. Además, se pueden implementar Azure Active Directory directivas de acceso condicional y directivas de cumplimiento de Intune para proteger la cuenta de recursos. Para obtener más información, vea [Acceso condicional compatible y directivas de cumplimiento de dispositivos Intune para Salas de Microsoft Teams](supported-ca-and-compliance-policies.md) y [Acceso condicional y cumplimiento de Intune para Salas de Microsoft Teams](conditional-access-and-compliance-for-devices.md)

Le recomendamos que cree la cuenta de recursos en Azure AD, si es posible. Aunque una cuenta sincronizada puede funcionar con Salas de Teams en implementaciones híbridas, estas cuentas sincronizadas a menudo tienen dificultades para iniciar sesión en Salas de Teams y pueden ser difíciles de solucionar. Si elige usar un servicio de federación de terceros para autenticar las credenciales de la cuenta de recursos, asegúrese de que el IDP de terceros responde con el `wsTrustResponse` atributo establecido en `urn:oasis:names:tc:SAML:1.0:assertion`.

## <a name="network-security"></a>Seguridad de red

Por lo general, Salas de Teams tiene los mismos requisitos de red que cualquier cliente de Microsoft Teams. El acceso a través de firewalls y otros dispositivos de seguridad es el mismo para Salas de Teams que para cualquier otro cliente de Microsoft Teams. Específica para Salas de Teams, las categorías enumeradas como "necesarias" para Teams deben estar abiertas en el firewall. Salas de Teams también necesita acceso a Windows Update, Microsoft Store y Microsoft Intune (si usas Microsoft Intune para administrar los dispositivos). Para obtener la lista completa de direcciones IP y URL necesarias para Salas de Microsoft Teams, consulte:

- **Microsoft Teams** [direcciones URL Office 365 e intervalos de direcciones IP](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams)
- **Windows Update** [Configurar WSUS](/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- **Requisitos previos de Microsoft Store** [para Microsoft Store para Empresas y educación](/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
- **Microsoft Intune** [puntos de conexión de red para Microsoft Intune](/mem/intune/fundamentals/intune-endpoints)

Si usa el componente de servicios administrados Salas de Microsoft Teams de Salas de Microsoft Teams Premium, también debe asegurarse de que Salas de Teams puede acceder a las siguientes direcciones URL:

- agent.rooms.microsoft.com
- global.azure-devices-provisioning.net
- gj3ftstorage.blob.core.windows.net
- iothubsgagwt5wgvwg6.azure-devices.net
- blobssgagwt5wgvwg6.blob.core.windows.net
- mmrstgnoamiot.azure-devices.net
- mmrstgnoamstor.blob.core.windows.net
- mmrprodapaciot.azure-devices.net
- mmrprodapacstor.blob.core.windows.net
- mmrprodemeaiot.azure-devices.net
- mmrprodemeastor.blob.core.windows.net
- mmrprodnoamiot.azure-devices.net
- mmrprodnoamstor.blob.core.windows.net

Salas de Teams se configura para mantenerse automáticamente parcheado con las últimas actualizaciones de Windows, incluidas las actualizaciones de seguridad. Salas de Teams instala todas las actualizaciones pendientes todos los días a partir de las 2:00 a.m. con una directiva local predefinida. No es necesario usar herramientas adicionales para implementar y aplicar las actualizaciones de Windows. El uso de herramientas adicionales para implementar y aplicar actualizaciones puede retrasar la instalación de Windows revisiones y, por tanto, llevar a una implementación menos segura. La aplicación Salas de Teams se implementa con la Microsoft Store. Si los dispositivos tienen licencia con Salas de Microsoft Teams Estándar, las nuevas versiones de la aplicación se instalan automáticamente durante el proceso de revisión nocturna. Si los dispositivos tienen licencia con Salas de Microsoft Teams Premium e inscritos en el Servicio administrado de Microsoft, se instalan nuevas versiones de la aplicación Salas de Teams según el plan de implementación definido.

Salas de Teams dispositivos funcionan con la mayoría de los protocolos de seguridad 802.1X u otros protocolos de seguridad basados en red. Sin embargo, no podemos probar Salas de Teams con todas las configuraciones de seguridad de red posibles. Por lo tanto, si surgen problemas de rendimiento que pueden rastrearse hasta problemas de rendimiento de la red, es posible que deba deshabilitar estos protocolos si están configurados en su organización.

Para obtener un rendimiento óptimo de los medios en tiempo real, le recomendamos que configure Teams tráfico multimedia para omitir los servidores proxy y otros dispositivos de seguridad de red. Los medios en tiempo real son muy sensibles a la latencia y los servidores proxy y los dispositivos de seguridad de red pueden degradar significativamente la calidad de audio y vídeo de los usuarios. Además, como Teams multimedia ya está cifrado, no hay ningún beneficio tangible de pasar el tráfico a través de un servidor proxy. Para obtener más información, consulte [Networking up (to the cloud): punto de vista de un arquitecto](/microsoft-365/solutions/networking-design-principles?view=o365-worldwide) que analiza las recomendaciones de redes para mejorar el rendimiento de los medios con Microsoft Teams y Salas de Microsoft Teams.

> [!IMPORTANT]
> Salas de Teams no admite servidores proxy autenticados.

Salas de Teams dispositivos no necesitan conectarse a una LAN interna. Considere la posibilidad de colocar Salas de Teams en un segmento de red seguro con acceso directo a Internet. Si su LAN interna se ve comprometida, las oportunidades de vectores de ataque hacia Salas de Teams se reducirán.

Te recomendamos encarecidamente que conectes tus dispositivos Salas de Teams a una red cableada. El uso de redes inalámbricas en Salas de Teams dispositivos no se recomienda ni está certificado. Algunas características de conectividad, como Wi-Fi Sense, están deshabilitadas de forma predeterminada.

Proximity Join y otras características de Salas de Teams dependen de Bluetooth. Sin embargo, la implementación Bluetooth en dispositivos Salas de Teams no permite una conexión de dispositivo externo a un dispositivo Salas de Teams. Bluetooth uso de la tecnología en dispositivos Salas de Teams está limitado actualmente a balizas publicitarias y conexiones próximas. El `ADV_NONCONN_INT` tipo de unidad de datos de protocolo (PDU) se usa en la baliza de publicidad. Este tipo de PDU es para dispositivos no conectables que anuncian información al dispositivo de escucha. No hay Bluetooth emparejamiento de dispositivos como parte de estas características. Encontrará más detalles sobre los protocolos de Bluetooth en el [sitio web de Bluetooth SIG](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/).
