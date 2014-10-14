class Securityquestions < ActiveRecord::Migration
  def up
   create_table  :securityquestions do |t|
     t.belongs_to :user
     t.string :question_1
     t.string :question_2
     t.string :question_3
     t.string :answer_1
     t.string :answer_2
     t.string :answer_3
     
     t.timestamps
   end
  end

  def down
    drop_table :securityquestions
  end
end
