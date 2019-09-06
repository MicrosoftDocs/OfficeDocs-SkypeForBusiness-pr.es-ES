---
title: Administrar de forma remota la configuración de la consola de salas de Microsoft Teams con un archivo de configuración XML
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
ms.collection: M365-voice
description: En este artículo se describe la administración remota de la configuración predeterminada usada por un dispositivo de salas de Microsoft Teams, incluida la aplicación de un tema personalizado.
ms.openlocfilehash: 916eca45a39e7bf0dfe6a35b5985832ef5d580f5
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "36774918"
---
# <a name="manage-a-microsoft-teams-rooms-console-settings-remotely-with-an-xml-configuration-file"></a>Administrar de forma remota la configuración de la consola de salas de Microsoft Teams con un archivo de configuración XML

En este artículo se describe la administración remota de la configuración predeterminada usada por un dispositivo de salas de Microsoft Teams, incluida la aplicación de un tema personalizado. Explica cómo crear un archivo de configuración maestra y vínculos a las discusiones sobre cómo colocarlos según sea necesario en los dispositivos administrados de forma remota.
  
Es posible cambiar la configuración predeterminada de los dispositivos administrados de forma remota mediante la actualización de un archivo XML maestro y el envío de copias a las consolas administradas. También puede implementar temas personalizados en las consolas de salas de Microsoft Teams con archivos de configuración XML.
  
## <a name="create-an-xml-configuration-file"></a>Crear un archivo de configuración XML

Cualquier editor de texto se puede usar para crear un archivo de configuración. En la tabla **elementos XML** se explican los elementos que se muestran en este ejemplo de archivo de configuración SkypeSettings. XML (nombre de archivo obligatorio).
  
```
<SkypeSettings>
    <AutoScreenShare>true</AutoScreenShare>
    <HideMeetingName>true</HideMeetingName>
    <UserAccount>
        <SkypeSignInAddress>RanierConf@contoso.com</SkypeSignInAddress>
        <ExchangeAddress>RanierConf@contoso.com</ExchangeAddress>
        <DomainUsername>Seattle\RanierConf</DomainUsername>
        <Password>password</Password>
        <ConfigureDomain>domain1, domain2</ConfigureDomain>
    </UserAccount>
    <IsTeamsDefaultClient>false</IsTeamsDefaultClient>
    <BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>
    <SkypeMeetingsEnabled>false</SkypeMeetingsEnabled>
    <TeamsMeetingsEnabled>true</TeamsMeetingsEnabled>
    <DualScreenMode>true</DualScreenMode>
    <SendLogs>
        <EmailAddressForLogsAndFeedback>RanierConf@contoso.com</EmailAddressForLogsAndFeedback>
        <SendLogsAndFeedback>true</SendLogsAndFeedback>
    </SendLogs>
    <Devices>
        <MicrophoneForCommunication>Microsoft LifeChat LX-6000</MicrophoneForCommunication>
        <SpeakerForCommunication>Realtek High Definition Audio</SpeakerForCommunication>
        <DefaultSpeaker>Polycom CX5100</DefaultSpeaker>
        <ContentCameraId>USB\VID_046D&amp;PID_0843&amp;MI_00\7&amp;17446CF2&amp;0&amp;0000</ContentCameraId>
        <ContentCameraInverted>false</ContentCameraInverted>
        <ContentCameraEnhancement>true</ContentCameraEnhancement>
    </Devices>
    <Theming>
        <ThemeName>Custom</ThemeName>
        <CustomThemeImageUrl>folder path</CustomThemeImageUrl>
        <CustomThemeColor>
            <RedComponent>100</RedComponent>
            <GreenComponent>100</GreenComponent>
            <BlueComponent>100</BlueComponent>
        </CustomThemeColor>
    </Theming>
</SkypeSettings>
```

Si un valor de variable es de un tipo incorrecto, los elementos están fuera de los pedidos, los elementos no se cierran, o se encuentra otro error, el archivo XML tiene un *formato incorrecto*. Al procesar un archivo XML de formato incorrecto, la configuración encontrada hasta el punto donde se produce el error se aplica el resto del archivo. Los elementos desconocidos que haya en el XML se ignoran. Si se omite un parámetro, este se queda igual en el dispositivo. Si un valor de parámetro no es válido, su valor anterior permanece sin modificar.
  
**Elementos XML**

|Elemento|Tipo|Nivel|Uso|
|:--- |:--- |:--- |:--- |
|\<SkypeSettings\> |Contenedor de todos los elementos. ||Obligatorio. |
| \<AutoScreenShare\>  |&#x2777; Boolean  |Primer &#x2776;  | Si se cumple, se habilita el uso compartido de pantalla automático.  |
|\<HideMeetingName\> |&#x2777; Boolean  |Primer &#x2776;  |Si se cumple, se ocultan los nombres de la reunión. |
|\<Cuentadeusuario\> |Contenedor |Primer &#x2776;  |Contenedor para parámetros de credenciales. La dirección de inicio de sesión, la dirección de Exchange o la dirección de correo electrónico suelen ser<span></span>iguales, como RanierConf @contoso. com. |
|\<SkypeMeetingsEnabled\>  |&#x2777; Boolean  |Primer &#x2776;  |Está habilitado de forma predeterminada. |
|\<SkypeSignInAddress\> |Cadena &#x2778;  ||El nombre de inicio de sesión de la SfB de la consola o de la cuenta de dispositivo de Teams. |
|\<ExchangeAddress\> |Cadena &#x2778;  ||El nombre de inicio de sesión para la cuenta del dispositivo de Exchange de la consola. Si se omite ExchangeAddress, SkypeSignInAddress no se volverá a usar automáticamente. |
|\<DomainUsername\> |Cadena &#x2778;  ||El dominio y el nombre de usuario del dispositivo de consola; por ejemplo, Seattle\RanierConf. |
|\<Contraseña\> |Cadena 3  || El parámetro de contraseña es la misma contraseña que se utiliza para iniciar sesión con la cuenta del dispositivo de Skype Empresarial.   |
| \<ConfigureDomain\>  |Cadena &#x2778;  ||Puede enumerar varios dominios, separados por comas. |
|\<TeamsMeetingsEnabled\> |&#x2777; Boolean  |Primer &#x2776;  |Está deshabilitado de forma predeterminada. <br/> <br/> El archivo XML se considera incorrecto si \<tanto SkypeMeetingsEnabled\> como\<TeamsMeetingsEnabled\> están deshabilitados, pero es aceptable que ambas configuraciones estén habilitadas al mismo tiempo. |
|\<IsTeamsDefaultClient> |&#x2777; Boolean  |Primer &#x2776;  |Está deshabilitado de forma predeterminada. |
|\<BluetoothAdvertisementEnabled> |&#x2777; Boolean  |Primer &#x2776;  |Está habilitado de forma predeterminada. |
|\<DualScreenMode\>  |&#x2777; Boolean  |Primer &#x2776;  |Si es verdadero, el modo de pantalla doble está habilitado. De lo contrario, el dispositivo usa el modo de pantalla simple. |
|\<SendLogs\> |Contenedor |Primer &#x2776;  ||
|\<EmailAddressForLogsAndFeedback\> |Cadena &#x2778;  || Establece una dirección de correo electrónico opcional a la que se pueden enviar los registros cuando aparece la ventana "enviar comentarios". |
|\<SendLogsAndFeedback\> |&#x2777; Boolean  || Si se cumple, los registros se envían al administrador. Si no se cumple, solo se envían los comentarios al administrador (y no los registros).  |
| \<Dispositivos\>  |Contenedor |Primer &#x2776;  | Los nombres de los dispositivos de audio conectados en los elementos secundarios son los mismos valores que aparecen en la aplicación del Administrador de dispositivos. La configuración puede contener un dispositivo que no existe actualmente en el sistema, como un dispositivo de A/V que no está conectado en este momento a la consola. La configuración se retendrá´para el dispositivo respectivo.  |
|\<MicrophoneForCommunication\> |Cadena &#x2778;  ||Establece el micrófono usado como dispositivo de grabación en una conferencia. |
|\<SpeakerForCommunication\> |Cadena &#x2778;  ||El dispositivo que se va a usar como altavoz en la conferencia. Esta configuración se usa para configurar el dispositivo de altavoz usado en una llamada. |
|\<DefaultSpeaker\> |Cadena &#x2778;  ||El dispositivo que se va a usar para reproducir el audio desde una fuente de transmisión por HDMI.  |
|\<ContentCameraId>  | Cadena &#x2778;  | | Defina la ruta de acceso de la instancia de la cámara configurada en el salón para compartir contenido de pizarra analógica en una reunión. Consulte [ubicar la ruta de acceso a la instancia USB de la cámara de contenido](#locate-the-content-camera-usb-instance-path).|
|\<ContentCameraInverted>  | &#x2777; Boolean | | Especifica si la cámara de contenido se instala físicamente al revés. Para las cámaras de contenido que admiten la rotación automática, especifique falso. |
|\<ContentCameraEnhancement>  | &#x2777; Boolean | |Cuando se establece en true (el valor predeterminado), la imagen de la cámara de contenido se ha mejorado digitalmente: se detecta la arista de la pizarra y se selecciona el zoom adecuado, se mejoran las líneas de tinta y la persona que escribe en la pizarra se hace transparente.  <br><br> Se establece en false si se desea enviar una fuente de video sin formato a los participantes de la reunión para los espacios donde no se ha dibujado una pizarra con un lápiz y en su lugar se usa la cámara para mostrar notas rápidas, pósteres u otros elementos multimedia.  |
| \<Temas\>  |Contenedor |Primer &#x2776;  |Una de las características que se pueden aplicar con un archivo XML es un tema personalizado para su organización. Puede especificar un nombre de tema, una imagen de fondo y un color. |
|\<ThemeName\> |Cadena &#x2778;  || Se usa para identificar el tema en el cliente. Las opciones de nombre de tema son la opción predeterminada, uno de los temas prestablecidos que se proporcionan o la opción personalizada. <br/>  Los nombres de temas personalizados siempre usan el nombre *personalizado*. La interfaz de usuario de cliente se puede establecer en la consola en el valor predeterminado o uno de los valores preestablecidos, pero un administrador debe configurar el uso de un tema personalizado de forma remota. <br/>  Los temas prestablecidos incluyen:  <br/>  Predeterminado <br/>  Ondas azules (Blue Wave) <br/>  Bosque digital (Digital Forest) <br/>  Atrapasueños (Dreamcatcher) <br/>  Limanada (Limeade) <br/>  Píxel perfecto (Pixel Perfect) <br/>  Mapa de ruta (Roadmap) <br/>  Atardecer (Sunset) <br/>  Para deshabilitar el tema actual, use "sin tema" para el ThemeName.  |
|\<CustomThemeImageUrl\> |Cadena &#x2778;  ||Necesario para un tema personalizado; en caso contrario, opcional.   |Para obtener más información sobre la imagen del tema personalizado, vea la sección [imágenes de temas personalizados](xml-config-file.md#Themes) .
|\<CustomThemeColor\> |Contenedor ||Contenedor de los \<valores\>RedComponent \<,\>GreenComponent y \<BlueComponent\> . Estos valores son obligatorios para un tema personalizado. |
|\<RedComponent\> |Byte (0-255) ||Representa el componente de color rojo. |
|\<GreenComponent\> |Byte (0-255) ||Representa el componente de color verde. |
|\<BlueComponent\> |Byte (0-255) ||Representa el componente de color azul. |
| | | |

&#x2776; todos los elementos de primer nivel son opcionales. Si un elemento del primer nivel se omite, todos sus parámetros secundarios permanecerán igual en el dispositivo.
  
&#x2777; un indicador booleano puede ser: true, false, 0 o 1. Si deja vacíos los valores booleanos o numéricos, puede representar el XML mal formado e impedir cambios en la configuración.
  
&#x2778; si un parámetro de cadena está presente y vacío, y Empty es un valor válido, el parámetro se borra en el dispositivo.
  
## <a name="manage-console-settings-with-an-xml-configuration-file"></a>Administrar la configuración de la consola con un archivo XML de configuración

En el inicio, si una consola de salones de Microsoft Teams encuentra un archivo XML denominado SkypeSettings `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`. XML que se encuentra en, aplica la configuración indicada por el archivo XML y, a continuación, elimina el archivo XML.
  
En función de Cuántos dispositivos de salas de Microsoft Teams tenga su empresa y de cómo elija administrarlos para configurarlos, hay varias maneras de ubicar el archivo de configuración XML. Una vez que el archivo se inserte en la consola, reinícielo para procesar los cambios en la configuración. El archivo XML de configuración se eliminará una vez que se procese correctamente. Los métodos de administración sugeridos para los dispositivos de salas de Microsoft Teams se tratan en:
  
- [Configuración de directivas de grupo para salas de Microsoft Teams](room-systems-v2-operations.md#GroupPolicy)
- [Administración remota con PowerShell](room-systems-v2-operations.md#RemotePS) y [configuración de un elemento de archivo](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)

Puede utilizar el método que desee, siempre que pueda usarlo para transferir archivos y desencadenar un reinicio en el dispositivo de consola. El archivo debe ser legible, grabable y eliminable por la cuenta de usuario local del dispositivo. Preferiblemente, es propiedad de y tiene privilegios completos para ese usuario. Si los permisos de archivo no se establecen correctamente, el software puede no aplicar la configuración, puede dar error al eliminar el archivo tras su procesamiento correctamente y puede incluso bloquearse.
  
## <a name="custom-theme-images"></a>Imágenes para temas personalizados

<a name="Themes"> </a>

El archivo de imagen del tema personalizado debe colocarse`C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` en la carpeta. Escriba el nombre de archivo y la extensión \<en\> la variable CustomThemeImageUrl.
  
El archivo de imagen debe tener exactamente 3840X1080 píxeles y debe ser uno de los siguientes formatos de archivo: jpg, JPEG, PNG y BMP. Si su organización quiere una imagen personalizada, un diseñador gráfico puede usar la [plantilla de Photoshop tema personalizado](https://go.microsoft.com/fwlink/?linkid=870441). Contiene más detalles sobre dónde se deben colocar varios elementos en una imagen de tema, y qué áreas aparecen en las consolas y las pantallas.
  
El archivo XML de configuración se debe actualizar al iniciarse el dispositivo para reconocer la imagen del tema. Una vez que el nuevo archivo XML se haya procesado y eliminado, el archivo de gráficos del tema se eliminará del directorio.
  
## <a name="locate-the-content-camera-usb-instance-path"></a>Ubicar la ruta de la instancia USB de la cámara de contenido

Para ubicar la ruta de acceso de la instancia:

1. Vaya a configuración de Windows en la consola de salones de Microsoft Teams.
2. Escriba la contraseña de administrador.
3. Desde un símbolo del sistema, `devmgmt.msc` escriba para abrir el administrador de dispositivos.
4. En el **Administrador de dispositivos**, mire en el nodo dispositivos de **imágenes** y busque la cámara de contenido.
5. Haga clic con el botón derecho en la cámara y Abra **propiedades**.
6. Seleccione la pestaña **detalles** y busque la propiedad de la ruta de acceso de la **instancia de dispositivo** en la lista desplegable.
7. El valor que se muestra es la ruta de instancia de dispositivo que se establece en el archivo de configuración XML. Al especificar la ruta de acceso en XML, reemplace el símbolo de y comercial `&amp;`(&) con.

## <a name="see-also"></a>Vea también

[Cámaras de contenido](content-camera.md)

[Administrar Salas de Microsoft Teams](skype-room-systems-v2.md)

[Configurar un elemento de archivo](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
