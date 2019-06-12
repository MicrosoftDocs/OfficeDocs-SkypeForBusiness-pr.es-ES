---
title: Administrar de forma remota la configuración de la consola de salas de Microsoft Teams con un archivo de configuración XML
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
ms.collection: M365-voice
description: En este artículo se describe la administración remota de la configuración predeterminada usada por un dispositivo de salas de Microsoft Teams, incluida la aplicación de un tema personalizado.
ms.openlocfilehash: 998702a7af98b72139b7f4f20916937ebf7fc247
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305336"
---
# <a name="manage-a-microsoft-teams-rooms-console-settings-remotely-with-an-xml-configuration-file"></a>Administrar de forma remota la configuración de la consola de salas de Microsoft Teams con un archivo de configuración XML
 
En este artículo se describe la administración remota de la configuración predeterminada usada por un dispositivo de salas de Microsoft Teams, incluida la aplicación de un tema personalizado.
  
Al actualizar un archivo XML maestro y enviar copias a las consolas que administra, le será posible cambiar la configuración predeterminada de los dispositivos administrados de forma remota. En este artículo se habla de cómo se crea un archivo como ese y se agregan vínculos a debates sobre cómo se colocan en los dispositivos administrados de forma remota. Con este método, también puede implementar temas personalizados en las consolas de salas de Microsoft Teams. 
  
## <a name="creating-an-xml-configuration-file"></a>Creación de un archivo de configuración XML

En la tabla siguiente se explican los elementos que se muestran en este archivo de configuración de SkypeSettings. XML de ejemplo (este es un nombre de archivo obligatorio). 
  
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

Si el archivo XML está mal formado (es decir, que un valor de variable es del tipo equivocado, los elementos están desordenados, los elementos están sin cerrar, etc.), la configuración se aplica hasta el momento en el que se genera el error y después el resto del archivo se ignora durante el procesamiento. Los elementos desconocidos que haya en el XML se ignoran. Si se omite un parámetro, este se queda igual en el dispositivo. Si el valor de un parámetro no es válido, su valor anterior permanece sin modificar.
  
**Elementos XML**
 
|Elemento|Tipo|Nivel|Uso|
|:--- |:--- |:--- |:--- |
|\<SkypeSettings\>   |Contenedor de todos los elementos.   ||Obligatorio.   |
| \<AutoScreenShare\>  |&#x2777; Boolean  |Primer &#x2776;  | Si se cumple, se habilita el uso compartido de pantalla automático.  |
|\<HideMeetingName\>   |&#x2777; Boolean  |Primer &#x2776;  |Si se cumple, se ocultan los nombres de la reunión.   |
|\<Cuentadeusuario\>   |Contenedor   |Primer &#x2776;  |Contenedor para parámetros de credenciales.   La dirección de inicio de sesión, la dirección de Exchange o la dirección de correo electrónico suelen ser<span></span>iguales, como RanierConf @contoso. com.   |
|\<SkypeMeetingsEnabled\>  |&#x2777; Boolean  |Primer &#x2776;  |Está habilitado de forma predeterminada.   |
|\<SkypeSignInAddress\>   |Cadena &#x2778;  ||El nombre de inicio de sesión para la cuenta del dispositivo de Skype Empresarial de la consola.   |
|\<ExchangeAddress\>   |Cadena &#x2778;  ||El nombre de inicio de sesión para la cuenta del dispositivo de Exchange de la consola.   Si se omite ExchangeAddress, SkypeSignInAddress no se volverá a usar automáticamente.    |
|\<DomainUsername\>   |Cadena &#x2778;  ||El dominio y el nombre de usuario del dispositivo de consola; por ejemplo, Seattle\RanierConf.   |
|\<Contraseña\>   |Cadena 3  || El parámetro de contraseña es la misma contraseña que se utiliza para iniciar sesión con la cuenta del dispositivo de Skype Empresarial.   |
| \<ConfigureDomain\>  |Cadena &#x2778;  ||Puede enumerar varios dominios, separados por comas.   |
|\<TeamsMeetingsEnabled\>   |&#x2777; Boolean  |Primer &#x2776;  |Está deshabilitado de forma predeterminada. <br/> <br/> El archivo XML se considera incorrecto si \<tanto SkypeMeetingsEnabled\> como\<TeamsMeetingsEnabled\> están deshabilitados, pero es aceptable que ambas configuraciones estén habilitadas al mismo tiempo.   |
|\<IsTeamsDefaultClient> |&#x2777; Boolean  |Primer &#x2776;  |Está deshabilitado de forma predeterminada. |
|\<BluetoothAdvertisementEnabled> |&#x2777; Boolean  |Primer &#x2776;  |Está habilitado de forma predeterminada. |
|\<DualScreenMode\>  |&#x2777; Boolean  |Primer &#x2776;  |Si es verdadero, el modo de pantalla doble está habilitado. De lo contrario, el dispositivo usará el modo de pantalla sencillo.   |
|\<SendLogs\>   |Contenedor   |Primer &#x2776;  ||
|\<EmailAddressForLogsAndFeedback\>   |Cadena &#x2778;  ||De esta forma se establece una dirección de correo electrónico opcional a la que se pueden enviar los registros cuando aparece la ventana "Enviar comentarios".    |
|\<SendLogsAndFeedback\>   |&#x2777; Boolean  || Si se cumple, los registros se envían al administrador. Si no se cumple, solo se envían los comentarios al administrador (y no los registros).  |
| \<Dispositivos\>  |Contenedor   |Primer &#x2776;  | Los nombres de los dispositivos de audio conectados en los elementos secundarios son los mismos valores que aparecen en la aplicación del Administrador de dispositivos. La configuración puede contener un dispositivo que no existe actualmente en el sistema, como un dispositivo de A/V que no está conectado en este momento a la consola. La configuración se retendrá´para el dispositivo respectivo.  |
|\<MicrophoneForCommunication\>   |Cadena &#x2778;  ||Establece el micrófono que se usará como dispositivo de grabación en una conferencia.   |
|\<SpeakerForCommunication\>   |Cadena &#x2778;  ||El dispositivo que se va a usar como altavoz en la conferencia. Esta configuración se utiliza para establecer el dispositivo de altavoz que se utilizará para escuchar el audio en una llamada.   |
|\<DefaultSpeaker\>   |Cadena &#x2778;  ||El dispositivo que se va a usar para reproducir el audio desde una fuente de transmisión por HDMI.    |
| \<Temas\>  |Contenedor   |Primer &#x2776;  |Una de las características que se van a aplicar mediante un archivo XML es un tema personalizado para la organización. Podrá especificar un nombre de tema, una imagen de fondo y un color.   |
|\<ThemeName\>   |Cadena &#x2778;  || Se usa para identificar el tema en el cliente. Las opciones de nombre de tema son la opción predeterminada, uno de los temas prestablecidos que se proporcionan o la opción personalizada. <br/>  Los nombres de temas personalizados siempre deben usar el nombre *personalizado* . La interfaz de usuario del cliente se puede establecer en la consola en Default (Predeterminado) o en una de las opciones prestablecidas, mientras que la aplicación de un tema personalizado la debe establecer de forma remota un administrador. <br/>  Los temas prestablecidos incluyen:  <br/>  Predeterminado <br/>  Ondas azules (Blue Wave) <br/>  Bosque digital (Digital Forest) <br/>  Atrapasueños (Dreamcatcher) <br/>  Limanada (Limeade) <br/>  Píxel perfecto (Pixel Perfect) <br/>  Mapa de ruta (Roadmap) <br/>  Atardecer (Sunset) <br/>  Para deshabilitar el tema actual, use "sin tema" para el ThemeName.  |
|\<CustomThemeImageUrl\>   |Cadena &#x2778;  ||Es obligatorio si se usa un tema personalizado; de lo contrario, es opcional. Consulte la sección [imágenes de temas personalizados](xml-config-file.md#Themes) a continuación para obtener más detalles sobre la imagen del tema personalizado.  |
|\<CustomThemeColor\>   |Contenedor   ||Contenedor de los \<valores\>RedComponent \<,\>GreenComponent y \<BlueComponent\> . Estos valores son obligatorios si se utiliza un tema personalizado.   |
|\<RedComponent\>   |Byte (0-255)   ||Representa el componente de color rojo.   |
|\<GreenComponent\>   |Byte (0-255)   ||Representa el componente de color verde.   |
|\<BlueComponent\>   |Byte (0-255)   ||Representa el componente de color azul.   |
| | | |
   
&#x2776; todos los elementos de primer nivel son opcionales. Si un elemento del primer nivel se omite, todos sus parámetros secundarios permanecerán igual en el dispositivo.
  
&#x2777; un marcador Boolean puede ser cualquiera de los siguientes: true, false, 0 o 1. Los valores booleanos o numéricos que se dejan en blanco pueden representar el XML malformado de manera que no habría cambios en la configuración.
  
 &#x2778; si un parámetro de cadena está presente, vacío y vacío es un valor válido, el parámetro se borra en el dispositivo.
  
## <a name="manage-console-settings-using-an-xml-configuration-file"></a>Administrar la configuración de la consola con un archivo XML de configuración

En el inicio, si una consola de salones de Microsoft Teams encuentra un archivo XML denominado SkypeSettings. XML en la ubicación **C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**, se aplicarán los parámetros de configuración indicado por el archivo XML y, a continuación, elimine el archivo XML.
  
En función de Cuántos dispositivos de salas de Microsoft Teams tenga su empresa y de cómo elija administrar para configurarlos, hay varias formas de colocar el archivo de configuración XML. Una vez que el archivo se inserte en la consola, reinícielo para procesar los cambios en la configuración. El archivo XML de configuración se eliminará una vez que se procese correctamente. Los métodos de administración sugeridos para los dispositivos de salas de Microsoft Teams se tratan en:
  
- [Configuración de directivas de grupo para salas de Microsoft Teams](room-systems-v2-operations.md#GroupPolicy)
    
- [Administración remota con PowerShell](room-systems-v2-operations.md#RemotePS) y [configuración de un elemento de archivo](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
    
Puede utilizar el método que desee, siempre que pueda usarlo para transferir archivos y desencadenar un reinicio en el dispositivo de consola. El archivo debe ser legible, grabable y eliminable por la cuenta de usuario local del dispositivo (preferiblemente, debe pertenecer a él y tener privilegios completos concedidos para ese usuario). Si los permisos de archivo no se establecen correctamente, el software puede fallar al aplicar la configuración, al eliminar el archivo tras su procesamiento e incluso podría bloquearse.
  
## <a name="custom-theme-images"></a>Imágenes para temas personalizados
<a name="Themes"> </a>

El archivo de imagen del tema personalizado debe colocarse en **C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**, solo tiene que escribir el nombre de \<archivo\> y la extensión en la variable CustomThemeImageUrl.
  
El archivo de imagen debe tener exactamente 3840 x 1080 píxeles y debe tener uno de los siguientes formatos de archivo: jpg, jpeg, png y bmp. Si su organización quiere una imagen personalizada, un diseñador gráfico encontrará útil la [plantilla de Photoshop tema personalizado](https://go.microsoft.com/fwlink/?linkid=870441) . Contiene más detalles sobre dónde se deben colocar varios elementos en una imagen de tema, y qué áreas aparecen en las consolas y las pantallas.
  
El archivo XML de configuración se debe actualizar al iniciarse el dispositivo para reconocer la imagen del tema. Una vez que el archivo XML nuevo se procese y se elimine, el archivo de gráficos del tema se eliminará del directorio.
  
## <a name="see-also"></a>Vea también


[Administrar Salas de Microsoft Teams](skype-room-systems-v2.md)

[Configurar un elemento de archivo](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
