---
title: Administrar la configuración de una consola de Sistemas de salas de Skype v2 de forma remota con un archivo XML de configuración
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
description: En este artículo se describe la administración remota de la configuración predeterminada utilizada por un dispositivo de v2 de sistemas de salón de Skype, incluyen la aplicación de un tema personalizado.
ms.openlocfilehash: 939b0ce13aac70a9a80b1cae246a9491b4c098de
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569162"
---
# <a name="manage-a-skype-room-systems-v2-console-settings-remotely-with-an-xml-configuration-file"></a>Administrar la configuración de una consola de Sistemas de salas de Skype v2 de forma remota con un archivo XML de configuración
 
En este artículo se describe la administración remota de la configuración predeterminada utilizada por un dispositivo de v2 de sistemas de salón de Skype, incluyen la aplicación de un tema personalizado.
  
Al actualizar un archivo XML maestro y enviar copias a las consolas que administra, le será posible cambiar la configuración predeterminada de los dispositivos administrados de forma remota. En este artículo se habla de cómo se crea un archivo como ese y se agregan vínculos a debates sobre cómo se colocan en los dispositivos administrados de forma remota. Con este método, también puede implementar los temas personalizados en las consolas de v2 de sistemas de salón de Skype. 
  
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
             <AutoRotatePassword>1</AutoRotatePassword>
  </UserAccount>    
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
 
|**Elemento**|**Tipo de**|**Nivel de**|**Uso**|
|:-----|:-----|:-----|:-----|
|\<SkypeSettings\>  <br/> |Contenedor de todos los elementos.  <br/> ||Obligatorio.  <br/> |
| \<AutoScreenShare\> <br/> |Valor booleano & #x 2777; <br/> |Primera & #x 2776; <br/> | Si se cumple, se habilita el uso compartido de pantalla automático. <br/> |
|\<HideMeetingName\>  <br/> |Valor booleano & #x 2777; <br/> |Primera & #x 2776; <br/> |Si se cumple, se ocultan los nombres de la reunión.  <br/> |
|\<UserAccount\>  <br/> |Contenedor  <br/> |Primera & #x 2776; <br/> |Contenedor para parámetros de credenciales.  <br/> Normalmente, el inicio de sesión en la dirección, dirección de Exchange o dirección de correo electrónico es los mismos, como RanierConf<span></span>@contoso.com.  <br/> |
|\<SkypeMeetingsEnabled\>  <br/> |Valor booleano & #x 2777; <br/> |Primera & #x 2776; <br/> |Está habilitada de forma predeterminada.  <br/> |
|\<TeamsMeetingsEnabled\>  <br/> |Valor booleano & #x 2777; <br/> |Primera & #x 2776; <br/> |Está deshabilitada de forma predeterminada.  <br/> El archivo XML se considera mal construida si ambos \<SkypeMeetingsEnabled\> y\<TeamsMeetingsEnabled\> están deshabilitadas, pero es aceptable tener ambas configuraciones habilitados al mismo tiempo.  <br/> |
|\<SkypeSignInAddress\>  <br/> |Cadena 3 <br/> ||El nombre de inicio de sesión para la cuenta del dispositivo de Skype Empresarial de la consola.  <br/> |
|\<ExchangeAddress\>  <br/> |Cadena 3 <br/> ||El nombre de inicio de sesión para la cuenta del dispositivo de Exchange de la consola.  <br/> Si se omite ExchangeAddress, SkypeSignInAddress no se volverá a usar automáticamente.   <br/> |
|\<Dominionombre_de_usuario\>  <br/> |Cadena & #x 2778; <br/> ||El dominio y el nombre de usuario del dispositivo de consola; por ejemplo, Seattle\RanierConf.  <br/> |
|\<Contraseña\>  <br/> |Cadena 3 <br/> || El parámetro de contraseña es la misma contraseña que se utiliza para iniciar sesión con la cuenta del dispositivo de Skype Empresarial.  <br/> |
| \<ConfigureDomain\> <br/> |Cadena & #x 2778; <br/> ||Puede enumerar varios dominios, separados por comas.  <br/> |
|\<AutoRotatePassword\>  <br/> |Valor booleano & #x 2777; <br/> |||
| \<DualScreenMode\> <br/> |Valor booleano & #x 2777; <br/> |Primera & #x 2776; <br/> |Si es true, se habilita el modo de pantalla dual. De lo contrario, el dispositivo usará el modo de pantalla sencillo.  <br/> |
|\<SendLogs\>  <br/> |Contenedor  <br/> |Primera & #x 2776; <br/> ||
|\<EmailAddressForLogsAndFeedback\>  <br/> |Cadena & #x 2778; <br/> ||De esta forma se establece una dirección de correo electrónico opcional a la que se pueden enviar los registros cuando aparece la ventana "Enviar comentarios".   <br/> |
|\<SendLogsAndFeedback\>  <br/> |Valor booleano & #x 2777; <br/> || Si se cumple, los registros se envían al administrador. Si no se cumple, solo se envían los comentarios al administrador (y no los registros). <br/> |
| \<Dispositivos\> <br/> |Contenedor  <br/> |Primera & #x 2776; <br/> | Los nombres de los dispositivos de audio conectados en los elementos secundarios son los mismos valores que aparecen en la aplicación del Administrador de dispositivos. La configuración puede contener un dispositivo que no existe actualmente en el sistema, como un dispositivo de A/V que no está conectado en este momento a la consola. La configuración se retendrá´para el dispositivo respectivo. <br/> |
|\<MicrophoneForCommunication\>  <br/> |Cadena 3 <br/> ||Establece el micrófono que se usará como dispositivo de grabación en una conferencia.  <br/> |
|\<SpeakerForCommunication\>  <br/> |Cadena 3 <br/> ||El dispositivo que se va a usar como altavoz en la conferencia. Esta configuración se utiliza para establecer el dispositivo de altavoz que se utilizará para escuchar el audio en una llamada.  <br/> |
|\<DefaultSpeaker\>  <br/> |Cadena 3 <br/> ||El dispositivo que se va a usar para reproducir el audio desde una fuente de transmisión por HDMI.   <br/> |
| \<Creación de temas\> <br/> |Contenedor  <br/> |Primera & #x 2776; <br/> |Una de las características que se van a aplicar mediante un archivo XML es un tema personalizado para la organización. Podrá especificar un nombre de tema, la imagen de fondo y el color.  <br/> |
|\<ThemeName\>  <br/> |Cadena & #x 2778; <br/> || Se usa para identificar el tema en el cliente. Las opciones de nombre de tema son la opción predeterminada, uno de los temas prestablecidos que se proporcionan o la opción personalizada. <br/>  Los nombres de tema personalizado siempre deben utilizar el nombre *personalizado* . La interfaz de usuario del cliente se puede establecer en la consola en Default (Predeterminado) o en una de las opciones prestablecidas, mientras que la aplicación de un tema personalizado la debe establecer de forma remota un administrador. <br/>  Los temas prestablecidos incluyen:  <br/>  Predeterminado <br/>  Ondas azules (Blue Wave) <br/>  Bosque digital (Digital Forest) <br/>  Atrapasueños (Dreamcatcher) <br/>  Limanada (Limeade) <br/>  Píxel perfecto (Pixel Perfect) <br/>  Mapa de ruta (Roadmap) <br/>  Atardecer (Sunset) <br/>  Para deshabilitar el tema actual, use "Sin tema" para el ThemeName. <br/> |
|\<CustomThemeImageUrl\>  <br/> |Cadena & #x 2778; <br/> ||Es obligatorio si se usa un tema personalizado; de lo contrario, es opcional. Vea la sección de [Imágenes personalizadas de tema](xml-config-file.md#Themes) siguiente para obtener más detalles en la imagen de tema personalizado. <br/> |
|\<CustomThemeColor\>  <br/> |Contenedor  <br/> ||Contenedor para la \<RedComponent\>, \<GreenComponent\>, y \<BlueComponent\> valores. Estos valores son obligatorios si se utiliza un tema personalizado.  <br/> |
|\<RedComponent\>  <br/> |Byte (0-255)  <br/> ||Representa el componente de color rojo.  <br/> |
|\<GreenComponent\>  <br/> |Byte (0-255)  <br/> ||Representa el componente de color verde.  <br/> |
|\<BlueComponent\>  <br/> |Byte (0-255)  <br/> ||Representa el componente de color azul.  <br/> |
   
& #x 2776; Todos los elementos de primer nivel son opcionales. Si un elemento del primer nivel se omite, todos sus parámetros secundarios permanecerán igual en el dispositivo.
  
& #x 2777; Un indicador booleano puede ser cualquiera de los siguientes valores: true, false, 0 o 1. Los valores booleanos o numéricos que se dejan en blanco pueden representar el XML malformado de manera que no habría cambios en la configuración.
  
 & #x 2778; Si un parámetro de cadena es presentar, vacío y vacío es un valor válido, se borra el parámetro en el dispositivo.
  
## <a name="manage-console-settings-using-an-xml-configuration-file"></a>Administrar la configuración de la consola con un archivo XML de configuración

En el inicio, si una consola de v2 de sistemas de salón de Skype busca un archivo XML denominado SkypeSettings.xml en la ubicación ** C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**, se aplicarán las opciones de configuración que se indican en el archivo XML, a continuación, elimine el archivo XML.
  
Dependiendo de cuántos dispositivos de sistemas de salón de Skype v2 tiene su empresa y la forma que elija Administrar para configurarlos, hay varias maneras para colocar el archivo de configuración XML. Una vez que el archivo se inserte en la consola, reinícielo para procesar los cambios en la configuración. El archivo XML de configuración se eliminará una vez que se procese correctamente. Los métodos de administración sugeridos para dispositivos de sistemas de salón de Skype v2 se tratan en:
  
- [Configurar la directiva de grupo para los Sistemas de salas de Skype v2](room-systems-v2-operations.md#GroupPolicy)
    
- [Administración remota con PowerShell](room-systems-v2-operations.md#RemotePS) y [configurar un elemento de archivo](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
    
Puede utilizar el método que desee, siempre que pueda usarlo para transferir archivos y desencadenar un reinicio en el dispositivo de consola. El archivo debe ser legible, puede escribir y eliminar poder mediante la cuenta de usuario local del dispositivo (preferiblemente, debe pertenecer a y tienen todos los privilegios concedidos a dicho usuario). Si los permisos de archivo no se establecen correctamente, el software puede fallar al aplicar la configuración, al eliminar el archivo tras su procesamiento e incluso podría bloquearse.
  
## <a name="custom-theme-images"></a>Imágenes para temas personalizados
<a name="Themes"> </a>

Se debe colocar el archivo de imagen de tema personalizado en **C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**, sólo tiene que escribir el nombre de archivo y la extensión en el \<CustomThemeImageUrl\> variable.
  
El archivo de imagen debe tener exactamente 3840 x 1080 píxeles y debe ser tener uno de los siguientes formatos de archivo: jpg, jpeg, png y bmp. Si su organización desea que una imagen personalizada, un diseñador gráfico útil nuestra [Plantilla personalizada de Photoshop de tema](https://go.microsoft.com/fwlink/?linkid=870441) . Contiene información detallada sobre dónde colocar diversos elementos en una imagen de tema y las áreas que aparecen en las consolas y muestra.
  
El archivo XML de configuración se debe actualizar al iniciarse el dispositivo para reconocer la imagen del tema. Una vez que el archivo XML nuevo se procese y se elimine, el archivo de gráficos del tema se eliminará del directorio.
  
## <a name="see-also"></a>Vea también
<a name="Themes"> </a>

[Administración de salón de Skype v2 de sistemas](skype-room-systems-v2.md)

[Configurar un elemento de archivo](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)