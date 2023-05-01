# spying-on-whatsapp
whatsapp/osint
@@ -27,7 +27,19 @@
'''	'''




def study_user(driver, user, language,excel):	def study_user(driver, user, language, excel):
	"""
	Generates an excel file with user data and checks their online status.
	Parameters:
	driver (webdriver): Selenium webdriver instance.
	user (str): The name of the user to study.
	language (str): The language of the user's WhatsApp account.
	excel (bool): Whether or not to generate an excel file.
	Returns:
	None
	"""
	# Create Excel File		# Create Excel File
	if excel:		if excel:
		excel = Converter()			excel = Converter()
@@ -121,6 +133,15 @@ def study_user(driver, user, language,excel):




def whatsapp_login():	def whatsapp_login():
	"""
	Logs into WhatsApp Web using Selenium and returns the driver object.
	Raises:
	- InvalidArgumentException: If a Selenium navigator is already running in the background.
	Returns:
	- driver: A webdriver object with WhatsApp Web open and the user logged in.
	"""
	try:		try:
		print('In order to make this program to work, you will need to log-in once in WhatsApp. After that, your session will be saved until you revoke it.')			print('In order to make this program to work, you will need to log-in once in WhatsApp. After that, your session will be saved until you revoke it.')
		options = webdriver.ChromeOptions()			options = webdriver.ChromeOptions()
@@ -140,6 +161,17 @@ def whatsapp_login():




def main():	def main():
	"""
	This function creates a table in the database and parses command line arguments.
	It then logs into WhatsApp and studies the specified user in the specified language.
	If the excel flag is set, it converts the database to an Excel file.
	Args:
	None
	Returns:
	None
	"""


	Database.create_table()		Database.create_table()
