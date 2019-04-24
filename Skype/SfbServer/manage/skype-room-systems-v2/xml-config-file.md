---
title: Administrar una configuración de la consola Microsoft salones de los equipos de forma remota con un archivo de configuración XML
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
ms.collection: M365-voice
description: En este artículo se describe la administración remota de la configuración predeterminada utilizada por un dispositivo de salas de equipos de Microsoft, que incluyen la aplicación de un tema personalizado.
ms.openlocfilehash: 2dc99046647fc1cbda8fcb7643dbdf06d2d24c82
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214746"
---
# <a name="manage-a-microsoft-teams-rooms-console-settings-remotely-with-an-xml-configuration-file"></a>Administrar una configuración de la consola Microsoft salones de los equipos de forma remota con un archivo de configuración XML
 
En este artículo se describe la administración remota de la configuración predeterminada utilizada por un dispositivo de salas de equipos de Microsoft, que incluyen la aplicación de un tema personalizado.
  
Al actualizar un archivo XML maestro y enviar copias a las consolas que administra, le será posible cambiar la configuración predeterminada de los dispositivos administrados de forma remota. En este artículo se habla de cómo se crea un archivo como ese y se agregan vínculos a debates sobre cómo se colocan en los dispositivos administrados de forma remota. Con este método, también puede implementar los temas personalizados en las consolas de salas de equipos de Microsoft. 
  
## <a name="creating-an-xml-configuration-file"></a>Creación de un archivo de configuración XML

En la tabla siguiente se explica los elementos que se muestra en este ejemplo SkypeSettings.xml (Esto es un nombre de archivo requerido) archivo de configuración. 
  
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

Si el archivo XML está mal formado (es decir, que un valor de variable es del tipo equivocado, los elementos están desordenados, los elementos están sin cerrar, etc.), la configuración se aplica hasta el momento en el que se genera el error y después el resto del archivo se ignora durante el procesamiento. Los elementos desconocidos que haya en el XML se ignoran. Si se omite un parámetro, este se queda igual en el dispositivo. Si el valor de un parámetro no es válido, su valor anterior permanece inalterado.
  
**Elementos XML**
 
|Elemento|Tipo|Nivel|Uso|
|:--- |:--- |:--- |:--- |
|\<SkypeSettings\>   |Contenedor de todos los elementos.   ||Obligatorio.   |
| \<AutoScreenShare\>  |_AMP_ Boolean #x 2777;  |Primera & #x 2776;  | Si se cumple, se habilita el uso compartido de pantalla automático.  |
|\<HideMeetingName\>   |_AMP_ Boolean #x 2777;  |Primera & #x 2776;  |Si se cumple, se ocultan los nombres de la reunión.   |
|\<UserAccount\>   |Contenedor   |Primera & #x 2776;  |Contenedor para parámetros de credenciales.   Normalmente, el inicio de sesión en la dirección, dirección de Exchange o dirección de correo electrónico es los mismos, como RanierConf<span></span>@contoso.com.   |
|\<SkypeMeetingsEnabled\>  |_AMP_ Boolean #x 2777;  |Primera & #x 2776;  |Está habilitado de forma predeterminada.   |
|\<SkypeSignInAddress\>   |Cadena & #x 2778;  ||El nombre de inicio de sesión para la cuenta del dispositivo de Skype Empresarial de la consola.   |
|\<ExchangeAddress\>   |Cadena & #x 2778;  ||El nombre de inicio de sesión para la cuenta del dispositivo de Exchange de la consola.   Si se omite ExchangeAddress, SkypeSignInAddress no se volverá a usar automáticamente.    |
|\<Dominionombre_de_usuario\>   |Cadena & #x 2778;  ||El dominio y el nombre de usuario del dispositivo de consola; por ejemplo, Seattle\RanierConf.   |
|\<Contraseña\>   |Cadena 3  || El parámetro de contraseña es la misma contraseña que se utiliza para iniciar sesión con la cuenta del dispositivo de Skype Empresarial.   |
| \<ConfigureDomain\>  |Cadena & #x 2778;  ||Puede enumerar varios dominios, separados por comas.   |
|\<TeamsMeetingsEnabled\>   |_AMP_ Boolean #x 2777;  |Primera & #x 2776;  |Está deshabilitado de forma predeterminada. <br/> <br/> El archivo XML se considera mal construida si ambos \<SkypeMeetingsEnabled\> y\<TeamsMeetingsEnabled\> están deshabilitadas, pero es aceptable tener ambas configuraciones habilitados al mismo tiempo.   |
|\<IsTeamsDefaultClient> |_AMP_ Boolean #x 2777;  |Primera & #x 2776;  |Está deshabilitado de forma predeterminada. |
|\<BluetoothAdvertisementEnabled> |_AMP_ Boolean #x 2777;  |Primera & #x 2776;  |Está habilitado de forma predeterminada. |
|\<DualScreenMode\>  |_AMP_ Boolean #x 2777;  |Primera & #x 2776;  |Si es true, se habilita el modo de pantalla dual. De lo contrario, el dispositivo usará el modo de pantalla sencillo.   |
|\<SendLogs\>   |Contenedor   |Primera & #x 2776;  ||
|\<EmailAddressForLogsAndFeedback\>   |Cadena & #x 2778;  ||De esta forma se establece una dirección de correo electrónico opcional a la que se pueden enviar los registros cuando aparece la ventana "Enviar comentarios".    |
|\<SendLogsAndFeedback\>   |_AMP_ Boolean #x 2777;  || Si se cumple, los registros se envían al administrador. Si no se cumple, solo se envían los comentarios al administrador (y no los registros).  |
| \<Dispositivos\>  |Contenedor   |Primera & #x 2776;  | Los nombres de los dispositivos de audio conectados en los elementos secundarios son los mismos valores que aparecen en la aplicación del Administrador de dispositivos. La configuración puede contener un dispositivo que no existe actualmente en el sistema, como un dispositivo de A/V que no está conectado en este momento a la consola. La configuración se retendrá´para el dispositivo respectivo.  |
|\<MicrophoneForCommunication\>   |Cadena & #x 2778;  ||Establece el micrófono que se usará como dispositivo de grabación en una conferencia.   |
|\<SpeakerForCommunication\>   |Cadena & #x 2778;  ||El dispositivo que se va a usar como altavoz en la conferencia. Esta configuración se utiliza para establecer el dispositivo de altavoz que se utilizará para escuchar el audio en una llamada.   |
|\<DefaultSpeaker\>   |Cadena & #x 2778;  ||El dispositivo que se va a usar para reproducir el audio desde una fuente de transmisión por HDMI.    |
| \<Creación de temas\>  |Contenedor   |Primera & #x 2776;  |Una de las características que se van a aplicar mediante un archivo XML es un tema personalizado para la organización. Podrá especificar un nombre de tema, la imagen de fondo y el color.   |
|\<ThemeName\>   |Cadena & #x 2778;  || Se usa para identificar el tema en el cliente. Las opciones de nombre de tema son la opción predeterminada, uno de los temas prestablecidos que se proporcionan o la opción personalizada. <br/>  Los nombres de tema personalizado siempre deben utilizar el nombre *personalizado* . La interfaz de usuario del cliente se puede establecer en la consola en Default (Predeterminado) o en una de las opciones prestablecidas, mientras que la aplicación de un tema personalizado la debe establecer de forma remota un administrador. <br/>  Los temas prestablecidos incluyen:  <br/>  Predeterminado <br/>  Ondas azules (Blue Wave) <br/>  Bosque digital (Digital Forest) <br/>  Atrapasueños (Dreamcatcher) <br/>  Limanada (Limeade) <br/>  Píxel perfecto (Pixel Perfect) <br/>  Mapa de ruta (Roadmap) <br/>  Atardecer (Sunset) <br/>  Para deshabilitar el tema actual, use "Sin tema" para el ThemeName.  |
|\<CustomThemeImageUrl\>   |Cadena & #x 2778;  ||Es obligatorio si se usa un tema personalizado; de lo contrario, es opcional. Vea la sección de [Imágenes personalizadas de tema](xml-config-file.md#Themes) siguiente para obtener más detalles en la imagen de tema personalizado.  |
|\<CustomThemeColor\>   |Contenedor   ||Contenedor para la \<RedComponent\>, \<GreenComponent\>, y \<BlueComponent\> valores. Estos valores son obligatorios si se utiliza un tema personalizado.   |
|\<RedComponent\>   |Byte (0-255)   ||Representa el componente de color rojo.   |
|\<GreenComponent\>   |Byte (0-255)   ||Representa el componente de color verde.   |
|\<BlueComponent\>   |Byte (0-255)   ||Representa el componente de color azul.   |
| | | |
   
& #x 2776; Todos los elementos de primer nivel son opcionales. Si un elemento del primer nivel se omite, todos sus parámetros secundarios permanecerán igual en el dispositivo.
  
& #x 2777; Un indicador booleano puede ser cualquiera de los siguientes valores: true, false, 0 o 1. Los valores booleanos o numéricos que se dejan en blanco pueden representar el XML malformado de manera que no habría cambios en la configuración.
  
 & #x 2778; Si un parámetro de cadena es presentar, vacío y vacío es un valor válido, se borra el parámetro en el dispositivo.
  
## <a name="manage-console-settings-using-an-xml-configuration-file"></a>Administrar la configuración de la consola con un archivo XML de configuración

En el inicio, si una consola de salas de equipos de Microsoft busca un archivo XML denominado SkypeSettings.xml en la ubicación **C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**, se aplicará las opciones de configuración indicada por el archivo XML, a continuación, elimine el archivo XML.
  
Dependiendo de cuántos dispositivos de salas de equipos de Microsoft tiene su empresa y la forma que elija Administrar para configurarlos, hay varias maneras para colocar el archivo de configuración XML. Una vez que el archivo se inserte en la consola, reinícielo para procesar los cambios en la configuración. El archivo XML de configuración se eliminará una vez que se procese correctamente. Se tratan los métodos de administración sugeridos para dispositivos de salas de equipos de Microsoft en:
  
- [Configuración de directiva de grupo para salas de equipos de Microsoft](room-systems-v2-operations.md#GroupPolicy)
    
- [Administración remota con PowerShell](room-systems-v2-operations.md#RemotePS) y [configurar un elemento de archivo](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
    
Puede utilizar el método que desee, siempre que pueda usarlo para transferir archivos y desencadenar un reinicio en el dispositivo de consola. El archivo debe ser legible, puede escribir y eliminar poder mediante la cuenta de usuario local del dispositivo (preferiblemente, debe pertenecer a y tienen todos los privilegios concedidos a dicho usuario). Si los permisos de archivo no se establecen correctamente, el software puede fallar al aplicar la configuración, al eliminar el archivo tras su procesamiento e incluso podría bloquearse.
  
## <a name="custom-theme-images"></a>Imágenes para temas personalizados
<a name="Themes"> </a>

Se debe colocar el archivo de imagen de tema personalizado en **C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**, sólo tiene que escribir el nombre de archivo y la extensión en el \<CustomThemeImageUrl\> variable.
  
El archivo de imagen debe tener exactamente 3840 x 1080 píxeles y debe tener uno de los siguientes formatos de archivo: jpg, jpeg, png y bmp. Si su organización desea que una imagen personalizada, un diseñador gráfico útil nuestra [Plantilla personalizada de Photoshop de tema](https://go.microsoft.com/fwlink/?linkid=870441) . Contiene más detalles sobre dónde se deben colocar varios elementos en una imagen de tema, y qué áreas aparecen en las consolas y las pantallas.
  
El archivo XML de configuración se debe actualizar al iniciarse el dispositivo para reconocer la imagen del tema. Una vez que el archivo XML nuevo se procese y se elimine, el archivo de gráficos del tema se eliminará del directorio.
  
## <a name="see-also"></a>Vea también


[Administrar Salas de Microsoft Teams](skype-room-systems-v2.md)

[Configurar un elemento de archivo](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
