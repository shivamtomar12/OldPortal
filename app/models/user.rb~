class User < ActiveRecord::Base
attr_accessible :username, :encrypted_password,:encrypted_password_confirmation, :salt, :email, :fname, :lname, :user_type, :session_token
has_one :securityquestion
validates :encrypted_password, presence: true, confirmation: true
validates :username, presence: true, uniqueness: true
validates :email, presence: true#, message: "Please enter email!!"
validates :fname, presence: true, length: { maximum: 30 }#, message: "Please enter your first name!!"
validates :lname, presence: true, length: { maximum: 30 }#, message: "Please enter your last name!!"
validates_exclusion_of :encrypted_password, in: ->(user) { [user.username, user.fname, user.lname] }, message: 'should not be the same as your username or first name'
validates_exclusion_of :username, in: %w( admin superuser ), message: "You don't belong here"
validates_format_of :email, with: /\A([^@\s]+)@((?:[-a-z0-9]+\.)+[a-z]{2,})\z/i, on: :create, message: "Invalid email format!!!" 
validates_format_of :username, with: /[a-zA-Z0-9]/, on: :create, message: "No special character, sorry!!"
validates_format_of :fname, with: /[a-zA-Z]/, on: :create, message: "How about checking your first name again!!"
validates_format_of :lname, with: /[a-zA-Z]/, on: :create, message: "How about checking your last name again!!"

validates_confirmation_of :encrypted_password, message: "Password does not match!!"
validates_presence_of :encrypted_password_confirmation, message: "Please confirm your password!!"

end
