---
title: "Informe de uso de RTC de Skype Empresarial"
ms.author: tonysmit
author: tonysmit
ms.date: 11/24/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 74eda791-c41f-4fd9-ae0b-913342e7ab04
description: "El nuevo Skype para área informes del centro de administración de empresas muestra audio y llamada conferencias actividad de su organización. Le permite explorar en profundidad los informes que le proporcione información más detallada sobre las actividades de cada usuario. Por ejemplo, puede usar el informe de Skype para obtener detalles de uso de RTC de empresa para ver el número de minutos de llamadas entrantes y salientes y el costo para estas llamadas. Puede ver los detalles de uso de RTC de conferencias de Audio incluido el costo de la llamada para que puedan comprender su uso y detalles de facturación para determinar el uso de la organización de llamadas."
---

# Informe de uso de RTC de Skype Empresarial

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades.  
  
El nuevo Skype para área **informes** del centro de administración de empresas muestra audio y llamada conferencias actividad de su organización. Le permite explorar en profundidad los informes que le proporcione información más detallada sobre las actividades de cada usuario. Por ejemplo, puede usar el informe de **Skype para obtener detalles de uso de RTC de empresa** para ver el número de minutos de llamadas entrantes y salientes y el costo para estas llamadas. Puede ver los detalles de uso de RTC de conferencias de Audio incluido el costo de la llamada para que puedan comprender su uso y detalles de facturación para determinar el uso de la organización de llamadas.
  
 Consulte[Informes de actividades en el Centro de administración de Office 365](http://technet.microsoft.com/library/0d6dfb17-8582-4172-a9a9-aed798150263%28Office.14%29.aspx) para ver los informes disponibles.
  
Este informe junto con lo otro Skype para los informes de empresa le ofrecen detalles en actividades como la llamada a uso en toda la organización. Estos detalles son muy útiles cuando se investigando, decisiones planificación y la realización de otras empresas para su organización y configurar [¿Qué son créditos de comunicaciones?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md).
  
> [!NOTE]
> Podrá ver todos los informes de Skype Empresarial cuando inicie sesión como administrador en el Centro de administración de Office 365. 
  
## Cómo acceder al informe Detalles de uso de RTC de Skype Empresarial

1. Vaya al **Centro de administración de Office 365** > haga clic en **los centros de administración** >, a continuación, haga clic en **Skype centro de administración de la empresa**
    
2. Desde la Skype centro de administración de negocio > Seleccionar **informes** desde el menú de la izquierda, a continuación, haga clic en **información de uso de RTC.**
    
    > [!NOTE]
    > Según la suscripción de Office 365 que tenga, puede que no vea todos los productos ni los informes que se muestran aquí. 
  
## Interpretar el informe Uso de RTC de Skype Empresarial

Puede obtener una vista en Skype del usuario para el uso de empresas RTC consultando cada una de las columnas que se muestran.
  
Este es el aspecto del informe.
  
![Skype for Business PSTN usage report.](../images/d3fee22a-a163-45c5-921a-45191288e0c8.png)
  
## 

|||
|:-----|:-----|
|**1** <br/> | La tabla muestra un desglose de todo el uso de RTC por usuario. Muestra todos los usuarios con Skype empresarial asignados a ellos y su uso de RTC. Se pueden agregar o quitar columnas a la tabla. <br/> **Identificador de llamada** es el identificador de llamada para una llamada. Es un identificador único para la llamada que se usa al llamar a soporte técnico de Microsoft. <br/> **Identificador de usuario** es el nombre de inicio de sesión del usuario. <br/> **Número de teléfono** es el Skype para el número de teléfono de la empresa que recibe la llamada para las llamadas entrantes o el número de marcado para las llamadas salientes. <br/> **Ubicación de usuario** es el país o región donde se encuentra el usuario. <br/> **Identificador de llamada** es el número de teléfono del llamador (identificador) para las llamadas entrantes, el número de que ha originado la llamada o el Skype para el número de empresa desde la que se ha originado la llamada para las llamadas salientes. <br/> **Tipo de llamada** es si la llamada fue un RTC entrante o saliente de llamadas y el tipo de llamada, como una llamada realizada por un usuario o una conferencia de audio. Los tipos de llamada, es posible que vea son: <br/> **Tipos de llamada de planes de llamada** <br/> **user_in** (el usuario recibe una llamada entrante de RTC) <br/> **user_out** (el usuario coloca una llamada saliente de RTC) <br/> **user_out_conf** (el usuario agregado a 2 o más participantes de RTC a la llamada, como una llamada de conferencia de 3 vías) <br/> **user_out_transfer** (el usuario transferir la llamada a un número de RTC) <br/> **user_out_forwarding** (el usuario reenviar la llamada a un número de RTC) <br/> **Tipos de llamada de conferencia de audio** <br/> **conf_in** (es decir, una llamada entrante para el puente de conferencia de Audio) <br/> **conf_out** (una llamada saliente que va desde el puente de conferencia de Audio normalmente para agregar un número de RTC a la conferencia) <br/>  Aplicaciones de comunicaciones unificadas (UCAP) <br/> **ucap_in** (es decir, una llamada entrante a la aplicación de UC como cola de llamada o de operador automático) <br/> **ucap_out** (una llamada de salida de la aplicación de UC como cola de llamada o de operador automático) <br/> **Nacional internacional** le indica si la llamada que se colocó consideró nacionales (dentro de un país o región) o internacional (fuera de un país o región) basado en la ubicación del usuario. <br/> **Marcados el destino** es el nombre del destino del país o región que se marca como Francia, Alemania o Estados Unidos (Estados Unidos). <br/> **Tipo de número** es el tipo de número de teléfono de número de teléfono de un usuario, un número gratuito de servicio o de pago. <br/> **Hora de inicio (UTC)** es la hora a la que se ha iniciado o realizado la llamada. <br/> **Duración** muestra el tiempo durante el cual ha estado conectada la llamada. <br/> **ConfID** es el identificador de conferencia de la conferencia de audio. <br/> **Cargo** es la cantidad de dinero o coste de la llamada que se carga a su cuenta. <br/> **Moneda** es el tipo de moneda que se usa para calcular el costo de la llamada. <br/> **La capacidad** es la licencia que utiliza para la llamada. Los tipos de licencia que es posible que vea son: <br/> **MCOPSTNPP** - créditos de comunicaciones <br/> **MCOPSTN1** - llamar a planear nacionales (3000 min US / min 1200 UE planes) <br/> **MCOPSTN2** - Plan de llamadas internacionales <br/> **MCOPSTN5** - nacionales llamar Plan (plan 120 minutos de llamadas) <br/> **MCOMEETADD** - audioconferencia <br/> **MCOMEETACPEA** - pago por minuto audioconferencia <br/> |
|**2** <br/> |Haga clic para arrastrar una columna a **Para agrupar por una columna concreta, arrastre y coloque el encabezado de columna aquí** si desea crear una vista que agrupe todos los datos de una o más columnas. <br/> |
|**3** <br/> |También puede exportar los datos del informe a un archivo .csv de Excel haciendo clic o tocando pulsando en el botón **Exportar a Excel**.  <br/> De esta forma se exportan los datos de todos los usuarios, a los que puede aplicar orden y filtros simples para realizar más análisis. Si tiene menos de 2000 usuarios, puede ordenar y filtrar dentro de la tabla en el mismo informe. Si tiene más de 2000 usuarios, para ordenar y filtrar tendrá que exportar los datos.  <br/> |
   
## ¿Desea ver otros informes de Skype Empresarial?

- [Informe de actividad de Skype Empresarial](skype-for-business-activity-report.md) Puede ver cuánto los usuarios utilizan punto a punto, organizada y participó en sesiones de conferencia.
    
- [Skype para el informe de uso del dispositivo de empresa](skype-for-business-device-usage-report.md) Puede para ver los dispositivos incluidos sistemas operativos basados en Windows y dispositivos móviles que tienen el Skype empresarial instalan y utilizan para mensajería instantánea y reuniones.
    
- [Informe de actividad de organizador de conferencias de Skype Empresarial](skype-for-business-conference-organizer-activity-report.md) Puede ver cuánto los usuarios están organizar conferencias que usar la mensajería instantánea, audio o vídeo, compartir aplicaciones, Web, /dial los fabricantes - 3 º y /dial  Microsoft.
    
- [Informe de actividad de participantes de conferencias de Skype Empresarial](skype-for-business-conference-participant-activity-report.md) Puede ver cuántas mensajería instantánea, audio y vídeo, uso compartido de aplicaciones, Web y acceso telefónico a conferencias de audio que se están participaron en.
    
- [Informe de actividad punto a punto de Skype Empresarial](skype-for-business-peer-to-peer-activity-report.md) Puede ver cuánto los usuarios utilizan mensajería instantánea, audio y vídeo, uso compartido de aplicaciones y transferencia de archivos.
    
- [Informe de bloqueados de Skype para los usuarios empresariales](skype-for-business-users-blocked-report.md) Puede ver los usuarios de su organización que se ha bloqueado de realizar llamadas de RTC.
    
- [Informe de bloqueados de Skype para los usuarios empresariales](skype-for-business-users-blocked-report.md) Puede ver los detalles sobre el tipo de medio que se usa, la duración de la sesión, el cliente que utiliza y la dirección URL de la conferencia.
    
## Temas relacionados

[Informes de actividades en el Centro de administración de Office 365](http://technet.microsoft.com/library/0d6dfb17-8582-4172-a9a9-aed798150263%28Office.14%29.aspx)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  

