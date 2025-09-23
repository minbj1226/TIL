## JOptionPane
-자주 사용하는 Dialog(InputDialog,  MessageDialog, ConfirmDialog)를 미리 제작하여 제공하는 클래스.

# InputDialog 
-사용자가 입력하는 값을 받기위한 다이얼로그

사용법)
``String msg=JOPtionPane.showInputDialog("메시지");`` 

# MessageDialog 
-사용자의 주의를 환기하기 위해서 사용하는 다이얼로그 

사용법)
``JOptionPane.showMessageDialog(null, "메시지를 표시할 내용");``

# ConfirmDialog
-사용자의 의사에 따라 추후 작업을 진행할지를 결정할 때 사용하는 dialog

사용법)
``int result = JOptionPane.showConfirmDialog(null, "정말 삭제하시겠습니까?", "확인", JOptionPane.YES_NO_CANCEL_OPTION);``
