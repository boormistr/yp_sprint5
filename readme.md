Обновил файл с логами.

Прошу прощения. Моя ошибка - не убрал исключение из gitignore. Сейчас логи есть.


В последней версии Rasa отсутствует параметр `--log-level` (в чате рекомендовали использовать именно последнюю версию Rasa).


Ниже приведён список того, что предлагает Rasa:

usage: rasa run [-h] [-v] [-vv] [--quiet] [--logging-config-file LOGGING_CONFIG_FILE] [-m MODEL] [--log-file LOG_FILE] [--use-syslog] [--syslog-address SYSLOG_ADDRESS] [--syslog-port SYSLOG_PORT] [--syslog-protocol SYSLOG_PROTOCOL] [--endpoints ENDPOINTS] [-i INTERFACE] [-p PORT] [-t AUTH_TOKEN] [--cors [CORS ...]] [--enable-api] [--response-timeout RESPONSE_TIMEOUT] [--request-timeout REQUEST_TIMEOUT] [--remote-storage REMOTE_STORAGE] [--ssl-certificate SSL_CERTIFICATE] [--ssl-keyfile SSL_KEYFILE] [--ssl-ca-file SSL_CA_FILE] [--ssl-password SSL_PASSWORD] [--credentials CREDENTIALS] [--connector CONNECTOR] [--jwt-secret JWT_SECRET] [--jwt-method JWT_METHOD] [--jwt-private-key JWT_PRIVATE_KEY] {actions} ... [model-as-positional-argument]


В связи с этим я сформировал конфигурационный файл `/rasa/log-config.yml`. Сами логи сохраняются в `/rasa/logs/rasa_logs.log`.

Пример логов:

2024-09-29 14:46:02,004 - h5py._conv - DEBUG - Creating converter from 7 to 5 2024-09-29 14:46:02,004 - h5py._conv - DEBUG - Creating converter from 5 to 7 2024-09-29 14:46:02,004 - h5py._conv - DEBUG - Creating converter from 7 to 5 2024-09-29 14:46:02,004 - h5py._conv - DEBUG - Creating converter from 5 to 7 2024-09-29 14:46:02,350 - jax._src.path - DEBUG - etils.epath was not found. Using pathlib for file I/O. 2024-09-29 14:46:03,394 - root - INFO - Starting Rasa server on http://0.0.0.0:5005 2024-09-29 14:46:03,561 - rasa.core.processor - INFO - Loading model models\20240922-201228-brute-delta.tar.gz... 2024-09-29 14:46:04,026 - urllib3.connectionpool - DEBUG - Starting new HTTPS connection (1): huggingface.co:443 2024-09-29 14:46:04,688 - urllib3.connectionpool - DEBUG - https://huggingface.co:443 "HEAD /bert-base-cased/resolve/main/tokenizer_config.json HTTP/11" 200 0 2024-09-29 14:46:04,961 - urllib3.connectionpool - DEBUG - https://huggingface.co:443 "HEAD /bert-base-cased/resolve/main/config.json HTTP/11" 200 0 2024-09-29 14:46:21,213 - root - INFO - Rasa server is up and running. 2024-09-29 14:46:21,214 - root - INFO - Enabling coroutine debugging. Loop id 2832995933472.