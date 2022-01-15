# Email-bomber
I have made this mini project for email bombing and having fun with friends it can be further used to time the emails and send an e-mail to multiple accounts
it gives us the option for gmail , yahoo and outlook with the smtplib libarary enjoy !!


smtplib --   An SMTP instance encapsulates an SMTP connection. It has methods that support a full repertoire of SMTP and ESMTP operations. If the optional host and port parameters are given, the SMTP connect() method is called with those parameters during initialization. If specified, local_hostname is used as the FQDN of the local host in the HELO/EHLO command. Otherwise, the local hostname is found using socket.getfqdn(). If the connect() call returns anything other than a success code, an SMTPConnectError is raised. The optional timeout parameter specifies a timeout in seconds for blocking operations like the connection attempt (if not specified, the global default timeout setting will be used). If the timeout expires, TimeoutError is raised. The optional source_address parameter allows binding to some specific source address in a machine with multiple network interfaces, and/or to some specific source TCP port. It takes a 2-tuple (host, port), for the socket to bind to as its source address before connecting. If omitted (or if host or port are '' and/or 0 respectively) the OS default behavior will be used.

class smtplib.SMTP_SSL(host='', port=0, local_hostname=None, keyfile=None, certfile=None, [timeout, ]context=None, source_address=None)

    An SMTP_SSL instance behaves exactly the same as instances of SMTP. SMTP_SSL should be used for situations where SSL is required from the beginning of the connection and using starttls() is not appropriate. If host is not specified, the local host is used. If port is zero, the standard SMTP-over-SSL port (465) is used. The optional arguments local_hostname, timeout and source_address have the same meaning as they do in the SMTP class. context, also optional, can contain a SSLContext and allows configuring various aspects of the secure connection. Please read Security considerations for best practices.

    keyfile and certfile are a legacy alternative to context, and can point to a PEM formatted private key and certificate chain file for the SSL connection.

    Changed in version 3.3: context was added.

    Changed in version 3.3: source_address argument was added.

    Changed in version 3.4: The class now supports hostname check with ssl.SSLContext.check_hostname and Server Name Indication (see ssl.HAS_SNI).

    Deprecated since version 3.6: keyfile and certfile are deprecated in favor of context. Please use ssl.SSLContext.load_cert_chain() instead, or let ssl.create_default_context() select the system’s trusted CA certificates for you.

    Changed in version 3.9: If the timeout parameter is set to be zero, it will raise a ValueError to prevent the creation of a non-blocking socket

class smtplib.LMTP(host='', port=LMTP_PORT, local_hostname=None, source_address=None[, timeout])

    The LMTP protocol, which is very similar to ESMTP, is heavily based on the standard SMTP client. It’s common to use Unix sockets for LMTP, so our connect() method must support that as well as a regular host:port server. The optional arguments local_hostname and source_address have the same meaning as they do in the SMTP class. To specify a Unix socket, you must use an absolute path for host, starting with a ‘/’.

    Authentication is supported, using the regular SMTP mechanism. When using a Unix socket, LMTP generally don’t support or require any authentication, but your mileage might vary.

    Changed in version 3.9: The optional timeout parameter was added.

A nice selection of exceptions is defined as well:

exception smtplib.SMTPException

    Subclass of OSError that is the base exception class for all the other exceptions provided by this module.

    Changed in version 3.4: SMTPException became subclass of OSError

exception smtplib.SMTPServerDisconnected

    This exception is raised when the server unexpectedly disconnects, or when an attempt is made to use the SMTP instance before connecting it to a server.

exception smtplib.SMTPResponseException

    Base class for all exceptions that include an SMTP error code. These exceptions are generated in some instances when the SMTP server returns an error code. The error code is stored in the smtp_code attribute of the error, and the smtp_error attribute is set to the error message.

exception smtplib.SMTPSenderRefused

    Sender address refused. In addition to the attributes set by on all SMTPResponseException exceptions, this sets ‘sender’ to the string that the SMTP server refused.

exception smtplib.SMTPRecipientsRefused

    All recipient addresses refused. The errors for each recipient are accessible through the attribute recipients, which is a dictionary of exactly the same sort as SMTP.sendmail() returns.

exception smtplib.SMTPDataError

    The SMTP server refused to accept the message data.

exception smtplib.SMTPConnectError

    Error occurred during establishment of a connection with the server.

exception smtplib.SMTPHeloError

    The server refused our HELO message.

exception smtplib.SMTPNotSupportedError

    The command or option attempted is not supported by the server.
