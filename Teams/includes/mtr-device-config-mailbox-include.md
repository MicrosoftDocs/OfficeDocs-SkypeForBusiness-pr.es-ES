
Puede mejorar su experiencia de reunión Salas de Teams personalizando cómo responde la cuenta de recursos a las invitaciones a reuniones y las procesa. Con Exchange Online PowerShell, puede establecer las siguientes propiedades de cuenta de recursos:

- **AutomateProcessing: `AutoAccept`** Los organizadores de la reunión reciben la decisión de reserva de la sala directamente sin la intervención humana.

- **AddOrganizerToSubject: `$false`** El organizador de la reunión no se agrega al asunto de la convocatoria de reunión.

- **DeleteComments: `$false`** Mantenga cualquier texto en el cuerpo del mensaje de las convocatorias de reunión entrantes. Esto es necesario para procesar reuniones externas de Teams y de terceros para proporcionar una experiencia de unirse a one touch.

- **DeleteSubject: `$false`** Mantenga el asunto de las convocatorias de reunión entrantes.

- **ProcessExternalMeetingMessages: `$true`** Especifica si se procesarán las convocatorias de reunión que se originen fuera de la organización de Exchange. Necesario para reuniones de Teams externas y [reuniones de terceros](/microsoftteams/rooms/third-party-join).

- **RemovePrivateProperty: `$false`** Garantiza que la marca privada que envió el organizador de la reunión en la convocatoria de reunión original permanece según lo especificado.

- **AddAdditionalResponse: `$true`** El texto especificado por el parámetro AdditionalResponse se agrega a las convocatorias de reunión.

- **AdditionalResponse: "¡Esta es una sala de reuniones de Microsoft Teams!"** El texto adicional que se agregará a la respuesta de aceptación de la reunión.

Para configurar estas propiedades, debe conectarse a Exchange Online PowerShell. Para obtener más información, vea [Conectarse a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps&preserve-view=true).

Después de conectarse a Exchange Online PowerShell, puede configurar las propiedades del buzón en una cuenta de recursos mediante el cmdlet [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

En el ejemplo siguiente se establecen las propiedades de la cuenta de `ConferenceRoom01` recursos:

``` PowerShell
Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -ProcessExternalMeetingMessages $true -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
```

