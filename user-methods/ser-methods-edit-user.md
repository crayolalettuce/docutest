Edit user settings.

HTTP method: POST /services/v1/users/edit
Client authorization: no
User authorization: required
TLS: required

Optional parameters
 email   - string Email address
 password  - string Password
 zip   - string Postal code
 first_name  - string First name
 last_name  - string Last name
 gender   - string Gender (“M” - male, “F” - female)
 daily_newsletter - boolean True if the user opts-in to the daily email
 is_21   - boolean True if the user is 21 years old or older
 tl_uid   - integer User’s Thrillist user ID
 approve  - boolean If true, approve the user (default: false)

**        birthday  - string User’s birthday; format is ISO 8601 date (i.e. YYYY-MM-DD, e.g. “1984-10-1”)**

Example request
        curl -k -d 'first_name=Jacinto&oauth_token=899419&oauth_token=fb18fc25e7e41608dadddcf567e9fe22' https://16.camp.jackthreads.com:9116/services/v1/users/edit

Example response
        {`
``   ``"success"``:``true``,``
``   ``"user"``:``{``
``      ``"uid"``:``899419``,``
``      ``"first_name"``:``"Jacinto"``,``
``      ``"last_name"``:``""``,``
``      ``"email"``:``"jacinto+cu11@thrillist.com"``,``
``      ``"birthday"``:``null``,``
``      ``"gender"``:``"M"``,``
``      ``"zip"``:``"10012"``,``
``      ``"username"``:``"jacintocu11"``,``
``      ``"subscriptions"``:``{``
``         ``"daily"``:``true``
``      ``}``,``
``      ``"tl_uid"``:``7548666``
``   ``}``
``}`