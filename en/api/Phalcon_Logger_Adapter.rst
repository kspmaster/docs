Class **Phalcon\\Logger\\Adapter**
==================================

Base class for Phalcon\\Logger adapters


Methods
---------

public  **setFormat** (*string* $format)

Set the log format



public *format*  **getFormat** ()

Returns the log format



protected *string*  **_applyFormat** ()

Applies the internal format to the message



public  **setDateFormat** (*string* $date)

Sets the internal date format



public *string*  **getDateFormat** ()

Returns the internal date format



public *string*  **getTypeString** (*integer* $type)

Returns the string meaning of a logger constant



public  **debug** (*string* $message)

Sends/Writes a debug message to the log



public  **error** (*string* $message)

Sends/Writes an error message to the log



public  **info** (*string* $message)

Sends/Writes an info message to the log



public  **notice** (*string* $message)

Sends/Writes a notice message to the log



public  **warning** (*string* $message)

Sends/Writes a warning message to the log



public  **alert** (*string* $message)

Sends/Writes an alert message to the log



public  **log** (*string* $message, *int* $type)

Logs a message



